# Testing the Nook test build

Thank you for testing Nook. This is an early, **unsigned** test build, so Windows Defender and SmartScreen may react to it. This prompt and configuration exist strictly for this unsigned test build and will be removed before a signed public release. Here is what to expect and what to do.

## Install

1. Download the installer from https://nook-download.vercel.app.
2. If Edge or Chrome says the file "isn't commonly downloaded", choose **Keep**, then **Keep anyway**.
3. If Windows SmartScreen says "Windows protected your PC", choose **More info**, then **Run anyway**.
4. Before copying any files, the installer asks whether to allow the Nook folder through Windows Defender:
   - **Yes**: Windows will ask for administrator permission (UAC) once. Approving it adds an exclusion for the Nook install folder only (`%LOCALAPPDATA%\Programs\Nook`) so Defender does not block it by mistake, then proceeds to install Nook. If permission was declined, you can choose to try again or cancel.
   - **No**: Cancels the installation immediately. No files are copied, no settings or registry values are written, and nothing is left behind on your PC.

## If Windows Defender removes Nook

Nook is new and unsigned, so Defender's machine-learning model can wrongly flag it (it may show a detection name such as `Trojan:Win32/Bearfoos.A!ml`). This is a false positive that we report to Microsoft with each build. If this happens:

1. Open **Windows Security**, then **Virus & threat protection**, then **Protection history**.
2. Open the Nook entry, choose **Actions**, then **Restore**.
3. To prevent it from happening again, go to **Virus & threat protection settings**, **Manage settings**, **Exclusions**, **Add or remove exclusions**, and add the folder `%LOCALAPPDATA%\Programs\Nook`.
4. If the binary was deleted instead of quarantined, download and run the installer again after adding the exclusion.

Only do this if you trust the source. You are getting this build directly from its developer.

## Remove the exclusion by hand

If you ever wish to remove Nook's Defender folder exclusion manually without uninstalling, open PowerShell as Administrator and run:

```powershell
Remove-MpPreference -ExclusionPath "$env:LOCALAPPDATA\Programs\Nook"
```

## Report a problem

Open an issue at https://github.com/adarzhpathade/nook-releases/issues and include your Windows 11 build number, your display refresh rate, and what you were doing. A screenshot or a short screen recording helps a lot.

## Remove Nook

Open **Settings** > **Apps** > **Installed apps**, locate **Nook**, and choose **Uninstall**. This automatically removes the Defender folder exclusion that the installer added, if you chose Yes.
