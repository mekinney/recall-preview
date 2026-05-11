# Installing Recall

This guide walks through installing **Recall** on Windows. Recall is
distributed as a single installer that sets up both the desktop UI
(`recall-wui`) and the background daemon.

> **Screenshots:** image paths below point to `docs/images/install/`.
> Capture each screenshot at the step indicated and drop it in that
> folder using the filename shown.

---

## Requirements

- Windows 10 (22H2) or Windows 11
- ~500 MB free disk space for the application
- Additional space for the index (varies with corpus size — budget
  roughly 2–5% of the size of the content you point Recall at)
- An account on the machine with permission to install applications

> Recall runs entirely locally. No account sign-up is required to
> install or use it.

---

## 1. Download the installer

Recall is currently distributed via private GitHub Releases. You will
receive a download link from the maintainer; the file is named
`recall-wui-Setup-<version>.exe`.

![Download page](images/install/01-download.png)

Save the installer somewhere you can find it (e.g. `Downloads`).

---

## 2. Run the installer

Double-click `recall-wui-Setup-<version>.exe`.

Windows SmartScreen may show a "Windows protected your PC" warning the
first time you run it. Click **More info** → **Run anyway**.

![SmartScreen prompt](images/install/02-smartscreen.png)

If a User Account Control prompt appears, click **Yes**.

---

## 3. Choose install location

The installer defaults to `%LOCALAPPDATA%\Programs\Recall`. Accept the
default unless you have a reason to change it.

![Install location step](images/install/03-location.png)

Click **Install**.

---

## 4. Wait for install to complete

Installation typically takes 10–30 seconds.

![Install progress](images/install/04-progress.png)

When it finishes, leave **Launch Recall** checked and click **Finish**.

![Install finished](images/install/05-finish.png)

---

## 5. First launch

On first launch, Recall opens to the welcome screen.

![Welcome screen](images/install/06-welcome.png)

---

## 6. Pick what to index

Recall asks which folders you want it to look at. Start small — a single
folder (e.g. `Documents`) is fine. You can add more later.

![Pick roots](images/install/07-pick-roots.png)

Click **Continue**.

---

## 7. Initial scan

The daemon begins scanning. The status bar shows progress. You can
start using Recall before the scan finishes — results fill in as
content is indexed.

![Scanning](images/install/08-scanning.png)

---

## 8. You're done

The main window is now ready. Type a query into the search box to
retrieve from your local content.

![Main window](images/install/09-main-window.png)

---

## Verifying the install

To confirm the daemon is running:

1. Open Task Manager (Ctrl+Shift+Esc).
2. Look for **recall-daemon.exe** under **Background processes**.

![Task Manager](images/install/10-task-manager.png)

If you don't see it, restart Recall from the Start menu.

---

## Updating

Recall checks for updates automatically on launch. When an update is
available, a notification appears in the bottom-right of the window.
Click it to install — the app restarts itself when the update is
applied.

![Update notification](images/install/11-update-notification.png)

---

## Uninstalling

1. Open **Settings → Apps → Installed apps**.
2. Find **Recall**, click the **…** menu, choose **Uninstall**.

![Uninstall via Settings](images/install/12-uninstall.png)

The uninstaller removes the application binaries. Your index database
and configuration in `%APPDATA%\Recall\` are left in place — delete
that folder manually if you also want to remove indexed data.

---

## Troubleshooting

- **Installer won't launch:** Right-click the `.exe` → **Properties** →
  check **Unblock** at the bottom → **Apply**, then retry.
- **App opens but search returns nothing:** The initial scan may still
  be running. Check the status bar at the bottom of the main window.
- **Daemon not running after launch:** See
  [docs/support/debugging-mcpb-install.md](support/debugging-mcpb-install.md)
  or file an issue with the maintainer.
