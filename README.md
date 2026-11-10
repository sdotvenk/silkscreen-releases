# silkscreen

Website and downloads for silkscreen, the AI bench partner for hardware integration. silkscreen is in public beta and free for personal use.

**[Download the latest release](https://github.com/sdotvenk/silkscreen-releases/releases/latest)**

This repository holds the website (served by GitHub Pages) and the release builds. The app's source code is not published here.

## Publishing a release

1. Open **Releases → Draft a new release**, create a tag such as `v0.1.0`, and give it a title and notes.
2. Upload the builds under exactly these file names, so the website's download buttons keep working for every release:

   | Platform | File |
   | --- | --- |
   | macOS (Apple silicon) | `silkscreen-mac-arm64.dmg` |
   | Windows installer | `silkscreen-win-x64-setup.exe` |
   | Windows portable | `silkscreen-win-x64-portable.zip` |
   | Linux AppImage | `silkscreen-linux-x86_64.AppImage` |
   | Linux Debian/Ubuntu | `silkscreen-linux-amd64.deb` |

   The Mac build already comes out under this name. The Windows and Linux builds don't yet, so rename those files before you upload them.

3. Update `version` in the `RELEASES` line of `install.html` (for example `"Beta 1.2"`) so the Download page shows the new version.

4. Publish it. The site links to `releases/latest/download/<file>`, which always points at the newest non-prerelease release. Pre-releases are not picked up by those links.

## Limits

- Each release file must be under 2 GiB, with up to 1,000 files per release. There is no cap on total release size or download bandwidth.
- The Pages site is limited to 1 GB, with a soft limit of 100 GB of traffic a month. Keep builds out of the git history and upload them to Releases instead. Git rejects files over 100 MB.

## Website

`index.html` and `install.html` are static pages. To serve them, open **Settings → Pages** and set the source to **Deploy from a branch**, using `main` and `/ (root)`.
