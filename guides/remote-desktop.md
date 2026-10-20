# NHH Remote Desktop (Virtual Machine)

Access to the remote desktop virtual machine is restricted to students who
requested access in advance. For those students, NHH provides a virtual desktop
infrastructure (VDI) running Windows with preconfigured course software.

The service runs on Omnissa Horizon (formerly VMware Horizon). You can access it
either through a native desktop client or through a web browser.

- Entry point:
  [https://desktop.nhh.no](https://desktop.nhh.no)

## Recommended: Omnissa Horizon Native Client

We recommend installing the native Omnissa Horizon Client instead of using the web
client. The native client offers:

- Higher performance and lower latency.
- Better display scaling and support for multiple monitors.
- Forwarding of system keyboard shortcuts (such as `Ctrl+C`, `Ctrl+V`, or `Alt+Tab`).
- Better clipboard and file sharing between your computer and the VM.

### Supported operating systems

- **Windows**: Windows 10 and Windows 11 (64-bit).
- **macOS**: Supported on both Apple Silicon (M-series) and Intel Macs running macOS
  14 (Sonoma) or newer. Older Intel Macs capped at earlier macOS versions cannot run
  the latest native client and should use the web client instead.
- **Linux**: Supported on distributions such as Ubuntu and RHEL (requires the X11
  display server; Wayland is not supported).

If you are on Windows or a supported macOS version, install the native client. If
you use Linux, ChromeOS, an unsupported macOS version, or cannot install software on
your machine, use the web client described below.

### Installation & setup

1. Open [https://desktop.nhh.no](https://desktop.nhh.no) in your web browser.
2. Click **Install Omnissa Horizon Client** or open the download page directly:

   [Omnissa Horizon Clients download](https://customerconnect.omnissa.com/downloads/info/slug/desktop_end_user_computing/omnissa_horizon_clients/8)

3. Download the installer for your operating system:
   - **Windows**: Download the Windows `.exe` installer. Run the installer and accept
     the default options.
   - **macOS**: Download the Universal `.dmg` installer. Open the `.dmg` file and drag
     `Omnissa Horizon Client` into your `Applications` folder.
4. Launch **Omnissa Horizon Client** from your Start Menu (Windows) or Applications
   folder (macOS).
5. Click **Add Server** (or **New Server**).
6. Enter `desktop.nhh.no` as the name of the Connection Server, then click **Connect**.
7. Log in using your NHH credentials (your student email ending in
   `@student.nhh.no` and password, followed by Microsoft multi-factor
   authentication).
8. Once authenticated, double-click the available desktop pool (such as the student
   virtual desktop) to start your session.

## Alternative: Omnissa Horizon Web Client

If you cannot install the native client or need quick access without setup, use the
browser client:

1. Open [https://desktop.nhh.no](https://desktop.nhh.no) in your browser.
2. Click **Omnissa Horizon Web Client**.
3. Sign in with your NHH credentials (your student email ending in
   `@student.nhh.no` and password) and complete multi-factor authentication.
4. Click the virtual desktop icon to launch the remote desktop inside your browser
   tab.

The web client works in any modern browser (Chrome, Edge, Safari, and Firefox), but
some keyboard shortcuts may be captured by your local browser rather than the remote
desktop.

## Saving your work

Virtual desktop sessions may not preserve local files across reboots.
Always save your code and data to an external location:

- Push your git repositories and commits to GitHub.
- Save files to your NHH OneDrive storage or another cloud provider.
