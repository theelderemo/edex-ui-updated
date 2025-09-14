
<p align="center">
  <br>
  <img alt="Logo" src="media/logo.png">
  <br>
  <br><br><br>
</p>

eDEX-UI is a fullscreen, cross-platform terminal emulator and system monitor that looks and feels like a sci-fi computer interface.

This is a community-driven fork of the original eDEX-UI, which was archived in October 2021. This fork aims to revive the project, apply security patches, and continue its development.

# 🛡️ Security Fix Information
- CVE: Not assigned (discovered post-archive)
- Severity: Critical
- Impact: Remote Command Execution via WebSocket hijacking

## Vulnerability Details
The original eDEX-UI contained a security vulnerability where malicious websites could connect to the internal terminal control WebSocket and execute arbitrary shell commands on the user's system.

## The Fix
This fork implements proper origin validation for WebSocket connections:
- Only accepts connections from the local Electron application (file:// protocol)
- Rejects all web-based connection attempts (http://, https://)
- Logs rejected connection attempts for security monitoring
- Fixed in: `src/classes/terminal.class.js`

---

# ⚠️ Important Notes

This is a fork of the original eDEX-UI, which is no longer actively maintained. While this fork addresses a critical security vulnerability, it should be considered a work in progress. Community contributions are welcome to help revive and improve the project. Please use this software "as-is" and take appropriate security measures when running any terminal emulator with network capabilities.

# Installation

## Building from Source (Recommended for Security)
Since this is a security-focused fork, building from source is the recommended way to ensure you have the patched version.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/](https://github.com/)[YOUR-USERNAME]/eDEX-UI-security-patched.git
    cd eDEX-UI-security-patched
    ```

2.  **Install dependencies and build the application for your operating system:**

    **Linux/macOS:**
    ```bash
    npm run install-linux # or install-darwin for macOS
    npm run build-linux  # or build-darwin for macOS
    ```

    **Windows (run as Administrator):**
    ```bash
    npm run install-windows
    npm run build-windows
    ```

### Pre-built Binaries

⚠️ **Note:** Pre-built binaries from the original repository contain the vulnerability. Only use builds from this fork or build from source.

---

# Contributing

Community contributions are highly encouraged! If you'd like to help, please feel free to:
-   **Report bugs:** Open an issue to report any bugs you find.
-   **Suggest features:** Open an issue to suggest new features or enhancements.
-   **Submit pull requests:** If you've made a change you'd like to contribute, please submit a pull request.

# Original Credits

eDEX-UI was created by [GitSquared (Gabriel Saillard)](https://github.com/GitSquared).

Sound effects by [IceWolf](https://soundcloud.com/iamicewolf).

Globe visualization by [Rob "Arscan" Scanlon](https://github.com/arscan).

# Security Fork Maintainer

This security-patched fork is maintained by [theelderemo](https://github.com/theelderemo).

If you discover any additional security issues, please report them by opening an issue in this repository.

# License

Licensed under the [GPLv3.0](https://github.com/GitSquared/edex-ui/blob/master/LICENSE), the same as the original project.
