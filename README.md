# DashDeck

DashDeck is a SimHub plugin that captures selected areas of a simulator and
shows them on VoCore displays, secondary monitors, phones, tablets, or OBS
browser sources.

It is designed for sim racing cockpits where a physical DDU hides part of the
main screen, and for extracting in-game mirrors, dashboards, or instruments
into dedicated physical displays.

## License and Public Releases

DashDeck is proprietary software. It is not open source.

Public release binaries, installers, documentation, and repository materials
are provided only under the included [End User License Agreement](EULA.md) and
[proprietary license](LICENSE.md).

No permission is granted to copy, modify, redistribute, reverse engineer,
decompile, disassemble, sell, sublicense, or create derivative or competing
software from this project, except where applicable law does not allow such a
restriction.

All rights are reserved by Bruno Silva.

## Requirements

- Windows 10 or Windows 11.
- SimHub with the plugin system enabled.
- .NET Framework 4.8 through SimHub.
- The Microsoft .NET 10 Runtime (x64) for the high-performance capture helper.
- At least one output:
  - a VoCore display managed by SimHub;
  - a secondary monitor;
  - a phone or tablet on the same network; or
  - an OBS browser source.

A VoCore display is optional.

## Main Features

- An Invisible dash that restores the part of the simulator hidden behind a
  physical DDU.
- Up to three additional screens for mirrors, dashboards, and instruments.
- One, two, or three selectable capture areas per Screen, with independent
  per-car geometry and Next/Previous Control Mapper actions.
- Independent VoCore, monitor, or Phone / Tablet / OBS output for each screen.
- Native, HD, and Full HD browser-stream resolutions, with GPU high-quality or
  sharpened resize before JPEG encoding.
- Phone and tablet keep-awake support, using the official Screen Wake Lock API
  when available and a one-tap silent-video fallback on HTTP LAN connections.
- A native-resolution visual area editor with aspect-ratio locking,
  tilted-display support, a draggable toolbar that moves away from the area
  being edited, and an integrated Screen/area selector.
- Per-car capture areas, including model-aware profiles for Le Mans Ultimate
  and rFactor 2 with vehicle-list caching and retry handling.
- Automatic rectangular and round VoCore handling.
- Fit, crop-fill, and stretch scaling with configurable image quality and frame
  limits.
- A configurable CAS rear-proximity overlay with resizable chevrons, names,
  scales and spotter alerts; multiple spotter styles; custom colours; presets;
  and live scenario previews for landscape, square, and round VoCore layouts.
- A touch-controlled web browser and dedicated YouTube/Twitch video player on
  rectangular VoCore displays.
- A virtual VoCore touchpad for controlling the Windows mouse from the cockpit.
- Custom idle screens made from images, animated GIFs, or short videos, with
  target-resolution previews and DPI-independent output scaling.
- SimHub Control Mapper actions for the most important screen and touchpad
  controls.
- Optional Stream Deck, Stream Deck +, Stream Dock and Ulanzi control through
  the shared SimHub Control Bridge.
- Built-in update checking and installation.

## Installation

1. Download `Install-DashDeck.exe` from the
   [latest release](https://github.com/BrunoSilva1978PT/DashDeck-Plugin-Public/releases/latest).
2. Close SimHub if the installer asks you to.
3. Accept the license terms and install the plugin.
4. Start SimHub and enable DashDeck if SimHub asks for confirmation.
5. Open **DashDeck** in SimHub and follow the built-in **Guide** tab.

The installer detects the SimHub installation and places `DashDeck.dll` in the
SimHub root folder. Advanced users can instead download `DashDeck.dll` and copy
it manually to the SimHub root folder, normally:

`C:\Program Files (x86)\SimHub`

Do not install the DLL in `SimHub\Plugins`.

If the required .NET 10 Runtime (x64) is missing, DashDeck offers to download
and run Microsoft's official installer. After a successful installation,
DashDeck restarts SimHub automatically so capture can start.

## Basic Setup

1. Open the **Screens** tab and enable the Invisible dash or one of the three
   mirror screens.
2. Choose the monitor that contains the area to capture.
3. For a mirror Screen, choose whether it needs one, two, or three selectable
   areas.
4. Select **Edit area on screen** and place the rectangle over the hidden dash,
   mirror, or instrument.
5. Choose a VoCore, secondary monitor, or Phone / Tablet / OBS output.
6. Load a car before editing a mirror screen so DashDeck can save its capture
   area to the correct car profile.

The Invisible dash is global. Mirror capture geometry is saved per car, while
the number of areas, active area, output, scaling, quality, CAS, and other
display options remain global. Bind the Screen's Next and Previous capture area
actions in SimHub Control Mapper to switch areas while driving.

See [GUIDE.md](GUIDE.md) for a more detailed introduction. The complete guide
is also available inside the plugin.

## Trial and Activation

DashDeck can be evaluated with a limited online trial. A lifetime license is
activated from the **License** tab using the email address entered during
checkout.

An activation can be removed from one PC and used again on another PC by the
same license holder.

[Purchase lifetime access on Ko-fi](https://ko-fi.com/s/56eb6d985f).

## Legal Notices

See [LICENSE.md](LICENSE.md), [EULA.md](EULA.md), and
[THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).
