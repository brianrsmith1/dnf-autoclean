#  DNF AutoClean

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)  
[![Fedora](https://img.shields.io/badge/Supported-Fedora%2038%2B-blue)](https://getfedora.org/)  

A lightweight tool for Fedora Linux that automatically cleans up old DNF packages and kernels — keeping your system lean, fast, and clutter-free.

---

##  Features
-  Automatically removes unused DNF packages
-  Keeps the **most recent kernels** (default: last 2)
-  Runs on a **configurable schedule** via `systemd`
-  Simple configuration in `/etc/dnf-autoclean.conf`
-  Includes installer (`install.sh`) for easy setup
-  Designed specifically for **Fedora Linux**

---

##  Installation

Clone the repo and run the installer:

```bash
git clone https://github.com/brianrsmith1/dnf-autoclean.git
cd dnf-autoclean
chmod +x install.sh
./install.sh

Uninstall at any time:

sudo dnf remove dnf-autoclean

⚙️ Configuration

Default config file:
/etc/dnf-autoclean.conf

Example:

[general]
retain_kernels = 2
schedule = weekly   # daily, weekly, or monthly

 Usage

Run manually:

sudo dnf-autoclean

Or let systemd handle it automatically according to your configured schedule.

Check service status:

systemctl status dnf-autoclean.timer

 Project Structure

dnf-autoclean/
├── install.sh
├── src/dnf-autoclean.sh
├── man/dnf-autoclean.1
├── packaging/dnf-autoclean.spec
├── .github/workflows/build.yml
└── LICENSE

🛠 Development

Build RPM package locally:

rpmbuild -ba packaging/dnf-autoclean.spec

Run tests (if applicable):

./tests/run-tests.sh






