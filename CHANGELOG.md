# Nook changelog

Nook is a test build for Windows 11. Newest first.

## v0.1.3

- **Fixed:** songs without an artist name no longer show a placeholder artist. Only the title is shown.
- **Fixed:** turning the microphone on or off from the call card no longer pops up a separate microphone message.
- **Removed:** the camera-in-use indicator. Camera use is no longer shown on the island.
- **Installer:** upgrading Nook into the same folder no longer asks the Windows Defender question again. If you install into a different folder, it asks once, allows the new folder and removes the old one. Uninstalling removes it.

## v0.1.2

- **Fixed:** calls and microphone use are now detected from live audio activity, so Google Meet in Chrome, Discord and other call apps show the call pill reliably.
- **Fixed:** the download page link preview now shows a card that matches the page.

## v0.1.1

- **New:** Smart mode keeps the pill visible over windowed apps and hides it only when an app is maximized.
- **New:** first-run defaults: Smart visibility, Tinted pill, Translucent surface at 70%, Bouncy motion, all activities on.
- **New:** the installer asks once, before installing, to allow the Nook folder through Windows Defender, because this unsigned test build can be flagged by mistake.
- **Fixed:** call, microphone and app name detection improvements.

## v0.1.0

- First test build.
