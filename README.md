# PyWipe

![Language](https://img.shields.io/badge/language-Python-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Python Version](https://img.shields.io/badge/python-%3E%3D3.7-blue.svg)

A command-line tool to reset your global Python environment.

`pywipe` acts as a 'factory reset' for your global Python installation, safely removing all user-installed packages while preserving essential ones like `pip` and `setuptools`. It's designed to clean up cluttered global environments without affecting your isolated virtual environments.

---

## Why PyWipe?

Over time, your global Python space can become a tangled mess of packages from various projects, leading to version conflicts, slower startup times, and the infamous "it works on my machine" syndrome. Manually cleaning this up is tedious and risky. PyWipe automates this process, providing a safe and reliable "factory reset" button for your Python environment.

---

## ✨ Features

*   🧹 **Clean Global Environment:** Uninstalls all packages installed in the global Python site-packages directory.
*   🛡️ **Essential Package Protection:** Automatically whitelists critical packages (`pip`, `setuptools`, etc.) to ensure your Python installation remains functional.
*   ✅ **Custom Whitelisting:** Allows you to specify additional packages to keep using the `--keep` option.
*   💾 **Automatic Backup:** Creates a timestamped backup file (`pywipe_backup_YYYY-MM-DD_HH-MM-SS.txt`) listing all installed packages before uninstallation, allowing for easy restoration if needed (though restoration is currently a manual process using `pip install -r <backup_file>`).
*   👀 **Dry Run Mode:** Use the `--dry-run` flag to see exactly which packages *would* be uninstalled without actually performing the action.
*   ⚠️ **Virtual Environment Safety:** Prevents accidental execution inside a virtual environment, protecting your isolated project dependencies.
*   ✨ **Rich Output:** Provides clear, colorful console output using the `rich` library.

---

## 📚 Tech Stack

*   **Python**
*   **Click:** For building the command-line interface.
*   **Rich:** For beautiful and informative console output.
*   **setuptools:** Standard Python package building tools.

---

## 🚀 Installation

`pywipe` is a Python package and can be installed globally using pip:

```bash
pip install pywipe
```

*Note: This tool is specifically designed for your global Python environment. Do not install or run it inside a virtual environment.*

---

## ▶️ Usage

Run the `pywipe run` command to initiate the cleanup process.

```bash
pywipe run
```

You will be shown a list of packages to be uninstalled (excluding essential and whitelisted packages) and prompted for confirmation before proceeding.

**Keep specific packages:**

Use the `--keep` or `-k` option followed by the package name to prevent it from being uninstalled. You can specify this option multiple times for different packages.

```bash
pywipe run --keep my-essential-tool --keep another-package-to-keep
```

**Dry run:**

To see which packages would be uninstalled without actually uninstalling them, use the `--dry-run` flag.

```bash
pywipe run --dry-run
```
**Restore:**
**Easy Restoration:** Quickly reinstall all packages from a backup file using the `restore` command.
```bash
pywipe restore --from pywipe_backup_2025-07-13_10-39-24.txt (add you actual file name).
```
---

🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

---

📝 License

Distributed under the MIT License.

---

**If PyWipe helped streamline your workflow, consider giving us a ⭐!**