# 🎵 Castlevania: Aria of Sorrow — High Quality Music

Replace the original **Castlevania: Aria of Sorrow** soundtrack with high-quality external WAV files while playing through **RetroArch + mGBA**.

The idea is simple:

> Keep the original game, gameplay and sound effects intact, while allowing any music track to be replaced by a higher-quality version.

You can replace **one track, several tracks, or the entire soundtrack**.

---

## 🎬 Video Demo

[![Watch the Aria of Sorrow HQ Music Mod](https://img.youtube.com/vi/Dm6gLcpuvKk/maxresdefault.jpg)](https://youtu.be/Dm6gLcpuvKk)

## ✨ Features

- 🎶 Replace individual Aria of Sorrow songs with external WAV files
- 🔊 Keeps the game's original sound effects
- 🎮 Works inside RetroArch using a modified mGBA core
- 🔁 Music changes automatically when the game changes tracks
- 💾 Works with save states
- 🎵 Missing WAV files automatically fall back to the original GBA music
- 🧩 Each song is identified by a simple number: `1.wav`, `2.wav`, `3.wav`, etc.
- 🖥️ Current release: **Windows**

---

## 📁 Installation

Download the project and open the included:

```text
RetroArch/
```

Copy its contents into your existing RetroArch installation.

The final structure should look like this:

```text
RetroArch/
├── cores/
│   └── mgba_libretro.dll
│
└── aria-high-quality-music/
    ├── 1.wav
    ├── 2.wav
    ├── 3.wav
    └── ...
```

The modified core automatically detects the RetroArch folder.

You **do not need to edit a drive letter or hard-code a path**.

For example, all of these installations can work:

```text
C:/RetroArch/
D:/Emulators/RetroArch/
E:/Games/RetroArch/
```

As long as the music folder is:

```text
RetroArch/aria-high-quality-music/
```

---

## 🚀 How to use it

### 1. Install the modified mGBA core

Copy:

```text
RetroArch/cores/mgba_libretro.dll
```

into your RetroArch `cores` folder.

### 2. Add your replacement music

Put your songs here:

```text
RetroArch/aria-high-quality-music/
```

### 3. Rename each song using its game ID

Example:

```text
1.wav
2.wav
3.wav
4.wav
```

The number determines which original game track will be replaced.

For example:

```text
2.wav = Ruined Castle Corridor
5.wav = Dance Hall
18.wav = Final Decisive Battle
```

You do **not** need to replace every song.

If `5.wav` exists, Dance Hall will use your external track.

If `6.wav` does not exist, Phantom Palace will continue using the original GBA music.

---

## 🎧 Required audio format

The WAV files must use:

```text
Format: WAV
Codec: PCM signed 16-bit
Sample rate: 32768 Hz
Channels: Mono or Stereo
```

If your WAV file uses another format, convert it with FFmpeg.

---

## 🛠️ Installing FFmpeg on Windows

Open PowerShell and run:

```powershell
winget install Gyan.FFmpeg
```

After installation, close and reopen PowerShell.

You can check that it works with:

```powershell
ffmpeg -version
```

---

## 🔄 Convert WAV files automatically

Put your source WAV files in a folder.

Inside that folder, open PowerShell and run:

```powershell
mkdir convertido -ErrorAction SilentlyContinue

Get-ChildItem *.wav | ForEach-Object {
    ffmpeg -y -i $_.FullName -ar 32768 -c:a pcm_s16le ("convertido\" + $_.Name)
}
```

The converted files will be created inside:

```text
convertido/
```

Then rename them according to the soundtrack list below:

```text
1.wav
2.wav
3.wav
...
```

> **Important:** Use audio that you own, created yourself, or have permission to use. This repository does not include the Castlevania ROM or copyrighted commercial soundtrack files. If you obtain audio from an online service such as YouTube, make sure your use complies with the rights holder's permissions and the service's terms.

---

# 🎼 Music ID / Set List

The filename must match the **ID** in the first column.

Example:

```text
Ruined Castle Corridor → 2.wav
Dance Hall             → 5.wav
Battle for the Throne  → 19.wav
```

| ID | Track | Recommended cover / reference |
|---:|---|---|
| 1 | Clock Tower | [YouTube](https://youtu.be/UtGuESr3z3o) |
| 2 | Ruined Castle Corridor | — |
| 3 | Underground Reservoir | — |
| 4 | Demon Castle Top Floor | [YouTube](https://www.youtube.com/watch?v=CfR11b5TNjk) |
| 5 | Dance Hall | [YouTube](https://youtu.be/_CCvzZXO0Ao) |
| 6 | Phantom Palace | [YouTube](https://youtu.be/FRk2AFP2Mjo) |
| 7 | Demon Castle Study | [YouTube](https://youtu.be/yDuValgn-zM) |
| 8 | Chapel | [YouTube](https://youtu.be/haOt3aNSs4U) |
| 9 | Forgotten Garden | [YouTube](https://youtu.be/qGixB_GycdE) |
| 10 | The Purgatory Arena | [YouTube](https://youtu.be/y2d-hoyGMNc) |
| 11 | Sacred Cave | [YouTube](https://www.youtube.com/watch?v=QPAuM6FgnKE) |
| 12 | Chaotic Realm | [YouTube](https://www.youtube.com/watch?v=7qQO7NxfBYQ) |
| 13 | Hammer Company | — |
| 14 | Name Entry | [YouTube](https://youtu.be/xxQMOe4DloE) |
| 15 | Game Over | [YouTube](https://youtu.be/1yfQ4Qs9HnI) |
| 16 | Confrontation | [YouTube](https://youtu.be/Yf-ly4f084E) |
| 17 | A Formidable Foe Appears | [YouTube](https://youtu.be/9jK4Lp63L1M) |
| 18 | Final Decisive Battle | [YouTube](https://youtu.be/9Hj9Wkol4i0) |
| 19 | Battle for the Throne | [YouTube](https://youtu.be/CuoQRZ2Hmyo) |
| 20 | Don't Wait Until Night | [YouTube](https://youtu.be/5dmlochO1lY) |
| 21 | Prologue ~ Mina's Theme | [YouTube](https://youtu.be/pxLQNgrGdog) |
| 22 | Premonition — Graham encounter | [YouTube](https://youtu.be/BcEBmYhBkpA) |
| 23 | Premonition — alternate/repeated entry | [YouTube](https://youtu.be/BcEBmYhBkpA) |
| 24 | Ending | [YouTube](https://www.youtube.com/watch?v=896UMQVOkcc) |
| 25 | Premonition — another variation | [YouTube](https://youtu.be/BcEBmYhBkpA) |
| 26 | Staff Roll | — |
| 27 | Black Sun — Game Intro | [YouTube](https://www.youtube.com/watch?v=HJKJYkVQCvw) |
| 28 | Sacred Cave — alternate entry | [YouTube](https://www.youtube.com/watch?v=QPAuM6FgnKE) |
| 29 | Prologue ~ Mina's Theme — alternate entry | [YouTube](https://youtu.be/pxLQNgrGdog) |
| 30 | Hammer Company — alternate entry | — |
| 31 | Battle Against Chaos | [YouTube](https://youtu.be/OY6ZW2vX3Ic) |
| 32 | Purification ~ Ending | [YouTube](https://www.youtube.com/watch?v=896UMQVOkcc) |
| 33 | Fate of the Devil | [YouTube](https://youtu.be/mBDfu8gxWuM) |
| 34 | Fate of the Devil — alternate entry | [YouTube](https://youtu.be/mBDfu8gxWuM) |
| 35 | You're Not Alone | [YouTube](https://youtu.be/XceEN_2tccs) |
| 36 | You're Not Alone — alternate entry | [YouTube](https://youtu.be/XceEN_2tccs) |
| 37 | Outdoor / Ambient 1 | — |
| 38 | Outdoor / Ambient 2 — Wind outside | — |
| 39 | Outdoor / Ambient 3 | — |
| 40 | Outdoor / Ambient 4 | — |
| 41 | Outdoor / Ambient 5 | — |
| 42 | Outdoor / Ambient 6 | — |
| 43 | Outdoor / Ambient 7 | — |
| 44 | Outdoor / Ambient 8 | — |
| 45 | Outdoor / Ambient 9 | — |

> ⚠️ **IDs 22–45 are still being tested and mapped.**  
> Some entries may be alternate references, ambience, duplicated music cues, or context-specific versions.

---

## 💡 Example

Suppose you only want to replace these three tracks:

```text
2  Ruined Castle Corridor
5  Dance Hall
18 Final Decisive Battle
```

Your folder only needs:

```text
RetroArch/
└── aria-high-quality-music/
    ├── 2.wav
    ├── 5.wav
    └── 18.wav
```

Everything else continues using the original GBA soundtrack.

---

## 🧠 How it works

Aria of Sorrow internally asks its sound engine to play songs using numeric IDs.

This modified mGBA core detects the song currently requested by the game.

When a matching external WAV exists:

```text
Game requests Song 5
        ↓
Core detects Song 5
        ↓
RetroArch/aria-high-quality-music/5.wav
        ↓
External high-quality music plays
```

The original background music for that song is muted, while the game's original sound effects continue normally.

If the WAV does not exist, the original GBA song plays as usual.

---

## 📦 What is included

```text
RetroArch/
├── cores/
│   └── modified mGBA core
└── aria-high-quality-music/
    └── place your WAV files here

Source Code/
└── modified source code
```

This project does **not** include:

- Castlevania: Aria of Sorrow ROM files
- Nintendo BIOS files
- Commercial soundtrack files
- Music files owned by third parties

You must provide your own legally obtained game and audio.

---

## 🖥️ Platform support

| Platform | Status |
|---|---|
| Windows + RetroArch | ✅ Supported |
| Xbox Series X/S + RetroArch Dev Mode | 🚧 Planned / separate version |

The first release focuses on Windows.

---

## ❤️ Why this project exists

Aria of Sorrow is one of the most loved Game Boy Advance Metroidvanias, but the GBA hardware heavily limits audio quality.

This project lets the game keep its original gameplay and sound effects while giving the soundtrack room to sound much closer to modern arrangements, remasters and covers.

The idea is not to change the game.

It is to let you choose **how its music sounds**.

---

## ⚠️ Disclaimer

This is an unofficial fan project and is not affiliated with or endorsed by Konami, Nintendo, RetroArch, Libretro or the mGBA project.

Castlevania and related names, characters and music are property of their respective rights holders.

The modified mGBA source should be distributed in accordance with the original project's applicable open-source license.
