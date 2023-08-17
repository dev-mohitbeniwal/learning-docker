# Docker Installation

## Installing Docker on Mac OS:

Prerequisites:

-   **Apple Silicon or Intel Chip:** Docker supports both.
-   **macOS Version:** macOS Mojave 10.14 or newer.
    Steps:

1. **Download Docker Desktop for Mac:**
    - Go to the Docker Desktop for Mac download page.
    - Choose the version suitable for your Mac (Apple Silicon or Intel Chip).
2. **Install Docker:**
    - Open the Docker.dmg file you downloaded.
    - Drag the Docker icon to the Applications folder.
3. **Start Docker:**
    - Navigate to Applications and open Docker.
    - You might be asked for permissions; grant them. Docker will now start setting up in the background.
4. **Docker Menu Bar:**
    - Once installed, you'll see a Docker icon in the top menu bar. This lets you access Docker settings, updates, and more.

## Docker Version Check:

Check Installed Version:

```bash
docker --version
```

This will show the version of Docker you've installed.

## Basic Troubleshooting for Mac:

1. **Docker Not Starting:** Restart Docker from the Docker menu in the top bar.
   Ensure you've granted all necessary permissions.
2. **Insufficient System Resources:** Docker requires some system resources to run smoothly. If you face performance issues, consider closing other heavy applications or increase Docker's allocated resources from the Preferences > Resources section.
3. **Update Issues:** If you're having issues updating Docker, consider downloading the latest version directly from the Docker website and reinstalling.
4. **Logs & Diagnostics:** For detailed logs and diagnostics, go to the Docker menu, then select Troubleshoot. Here, you can view logs or run diagnostic tests.

### [Previous Topic: Installation](/Docker/Installation.md)

### [Previous Topic: Basics](/Docker/Basics.md)
