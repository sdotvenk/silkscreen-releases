# silkscreen

Website and downloads for silkscreen, the AI bench partner for hardware integration. silkscreen is in public beta and free for personal use.

**[Download the latest release](https://github.com/sdotvenk/silkscreen-releases/releases)**

This repository holds the website (served by GitHub Pages) and the release builds. The app's source code is not published here.

## Publishing a release

1. Open **Releases → Draft a new release**, create a tag such as `v1.2.0`, and give it a title and notes.
2. Upload the builds as electron-builder names them, `silkscreen-<version>-<platform>`:

   | Platform | File |
   | --- | --- |
   | macOS (Apple silicon) | `silkscreen-1.2.0-mac-arm64.dmg` |
   | Windows installer | `silkscreen-1.2.0-win-x64.exe` |
   | Windows portable | `silkscreen-1.2.0-win-x64.zip` |
   | Linux AppImage | `silkscreen-1.2.0-linux-x86_64.AppImage` |
   | Linux Debian/Ubuntu | `silkscreen-1.2.0-linux-amd64.deb` |

3. Publish it, then update `install.html`: set `TAG` and `VER` (for example `"v1.2.0"` and `"1.2.0"`) and `version` (for example `"Beta 1.2"`). The download buttons link to that exact release, so they work for pre-releases too.

## Limits

- Each release file must be under 2 GiB, with up to 1,000 files per release. There is no cap on total release size or download bandwidth.
- The Pages site is limited to 1 GB, with a soft limit of 100 GB of traffic a month. Keep builds out of the git history and upload them to Releases instead. Git rejects files over 100 MB.

## Website

The site is live at https://trysilkscreen.com (DNS at Namecheap, pointed at GitHub Pages; the `CNAME` file holds the domain, so keep it).

`index.html` and `install.html` are static pages. To serve them, open **Settings → Pages** and set the source to **Deploy from a branch**, using `main` and `/ (root)`.
