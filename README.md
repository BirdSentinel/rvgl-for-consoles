# RVGL Console Ports

<p align="center">
  <img src="https://rvgl.org/imgs/rvgl_logo.png" alt="RVGL"/>
</p>
Six console ports of RVGL, sharing the original C++ engine, physics, AI and game formats. Each target adapts rendering, audio, input and storage to its platform.

All versions below are based on **23.1030a1 version**, and they support **cross-platform online** multiplayer.

| Platform / version | Custom content | Split-screen | How it runs | Online | Notes |
| --- | --- | --- | --- | --- | --- |
| Wii | Yes; memory limits apply | Up to 4 | 480p with 60fps on stock tracks with 8 cars | Works on Dolphin, unverified on real hardware | 512px texture cap |
| GameCube | Yes; memory limits apply | Up to 4 | 480p with 60fps on stock tracks with 4 cars | Works on Dolphin, unverified on real hardware | 128/256px textures, unverified on real hardware |
| Switch | Yes | Up to 4  | 720p/1080p with 60fps on stock tracks with 8 cars | Works on real hardware | - |
| PSP | Yes; memory limits apply | No | Native PSP resolution, targeting 30fps with 4 cars | Works on PPSSPP, unverified on real hardware | Needs 64MB memory, PSP-1000 is not supported |
| PS3 | Yes | Up to 4 | 720p with 60fps on stock tracks with 8 cars | Works on real hardware | - |
| Xbox 360 | Yes | Up to 4| 720p with 60fps on stock tracks with 8 cars | Works on real hardware | - |

Custom-content support means the port can load additional assets, not that every community track fits its memory budget. FPS caps and render resolutions are settings, not guaranteed performance.

## Under the hood

- **Wii:** devkitPPC/libogc builds the engine into native PowerPC code. OpenGX maps legacy rendering to GX, SDL2 handles platform services, with PCM effects and streamed music.
- **GameCube:** shares the Wii GX backend, with tighter texture and memory budgets. Effects use ARAM and audio DMA, networking uses the Broadband Adapter.
- **Switch:** Built with devkitPro, using OpenGL ES for rendering. Runs as an NRO homebrew application.
- **PSP:** PSPSDK GU/GE submits geometry directly to the GPU. An indexed asset archive reduces file access, while native audio threads mix effects and stream ADPCM music.
- **PS3:** PSL1GHT drives native RSX shaders for the legacy drawing path. Controller menus, SDL audio and libnet-backed ENet complete the platform layer.
- **Xbox 360:** XSDK toolchain produces a XEX with native Xenos rendering and controller input.

## How to install

Acquire the RVGL files from [here](https://distribute.re-volt.io/releases/rvgl_full_win64_original.zip) *(you don't need the dlls and the exe)*.

### Wii
Download the [Wii DOL](https://github.com/BirdSentinel/rvgl-for-consoles/releases) from the releases page. Copy the files to the root of your SD/USB and put the RVGL files in the empty "rvgl" folder, then launch it from Homebrew Launcher.

### Gamecube
Download the [GC DOL](https://github.com/BirdSentinel/rvgl-for-consoles/releases) from the releases page. Copy the files to your SD card and put the RVGL files in the empty "rvgl" folder, then launch it from Swiss.

### Switch
Open the [rvgl-for-switch](https://github.com/BirdSentinel/rvgl-for-switch) repo and follow the instructions.

### PSP
Download the [PSP Pack](https://github.com/BirdSentinel/rvgl-for-consoles/releases) from the releases page, copy to PSP/GAME/RVGL and launch it from the XMB. *(The converted RVGL files already in the PSP Pack)*

### PS3
Download the [PS3 EBOOT](https://github.com/BirdSentinel/rvgl-for-consoles/releases) from the releases page. Copy the files to /dev_hdd0/game/RVGL00001 and put the RVGL content to the USRDIR folder.

### Xbox 360
Download the [360 XEX](https://github.com/BirdSentinel/rvgl-for-consoles/releases) from the releases page. Copy the files to your HDD or USB, and then put the RVGL content to the "rvgl" folder, launch it with default.xex
