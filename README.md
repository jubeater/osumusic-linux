# osu!music-linux

> **Linux build of the original [osu!music](https://github.com/xtx-code/osumusic) project.**
>
> This repository exists to package and run the original project on Linux. The
> concept, design, and original implementation belong to **tonixtx**. Please
> direct all original-project credit and recognition to the upstream author.

Upstream repository: https://github.com/xtx-code/osumusic

<p align="center">
  <img src="assets/screenshot-desktop.png" width="350" alt="Mobile Design" align="left" style="margin-right: 20px;" />

</p>



**About**

This application automatically detects your local osu! installation and allows you to browse and play your beatmaps seamlessly.
Minimalist music player for your **osu! beatmaps** library, designed with the sleek aesthetics of **osu!lazer** in mind. Built for situations when you can’t or don’t want to play osu!, but still want to listen to the music from beatmaps.

**Features**

- **Lazer-Inspired UI**: Interface with vibrant card backgrounds and smooth animations.
- **Beatmap Integration**: Automatically detects and plays music directly from your osu! installation.
- **Search**: Real-time filtering with support for Unicode titles and artist names.
- **Audio**: Playback powered by Howler.js.

<br clear="left"/>

<details>
<summary><b>View fullsize window</b></summary>

<br>

<img src="assets/screenshot-mobile.png" width="100%" alt="Desktop Design" />

</details>

## Installation

### Linux

**Tested only on Ubuntu 26.04.** Compatibility with other Linux distributions
has not been verified.

Build the AppImage and Debian package with:

```bash
npm install
npm run dist
```

The app looks for a native osu!lazer installation at `$XDG_DATA_HOME/osu`, or
`~/.local/share/osu` when `XDG_DATA_HOME` is not set. For a custom location,
set `OSU_LAZER_PATH` to the directory containing `client.realm` before launching.

## CI/CD and Releases

GitHub Actions builds the project on every push to `main` and every pull request.
To publish Linux installers, update the version in `package.json`, commit the
change, and push a matching version tag:

```bash
git add package.json
git commit -m "release v2.3.82"
git push
git tag v2.3.82
git push origin v2.3.82
```

Tags beginning with `v` automatically create a GitHub Release containing the
AppImage and Debian package. The workflow runs on Ubuntu 24.04; the application
itself has only been tested on Ubuntu 26.04.

## Tech Info

Frontend: React 19 + TypeScript + Vite
Animations: Framer Motion
Desktop: Electron 40.6.0
Database: Realm (MongoDB)
AI: Copilot (Github 😎)

Original project by [tonixtx](https://github.com/xtx-code).
