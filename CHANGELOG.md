# Changelog

## 1.3.0 - 2026-07-24

- Migrated the high-performance Desktop Duplication capture helper from .NET 8
  to .NET 10.
- Added reliable detection of the required Microsoft .NET 10 Runtime (x64).
- Added a built-in Install action that downloads and launches Microsoft's
  official runtime installer when it is missing.
- DashDeck now verifies that the runtime installation succeeded and restarts
  SimHub automatically so capture can start.
- Improved the missing-runtime prompt and corrected capture performance logs
  to identify frames as received from the external helper.

## 1.2.0 - 2026-07-24

- Added one, two, or three selectable capture areas to Screen 1, Screen 2, and
  Screen 3. Area count is global, while each area's coordinates, tilt, and
  source monitor remain per car.
- Added Next and Previous capture area controls and Control Mapper roles for
  each Screen, with wrap-around switching in both directions.
- Allowed capture areas to be added, removed, and selected without a car
  loaded; kept their coordinates visible; added removal confirmation; and made
  unavailable geometry controls visually distinct.
- Fixed coordinate and tilt edits so they immediately update the selected
  capture area without making it disappear from the UI.
- Made idle-theme rendering and previews use the target's real pixel
  resolution, independently of Windows display scaling.
- Expanded the CAS overlay with appearance presets, independently resizable
  elements, configurable name-plate opacity, three spotter styles, custom
  colours, optional details, and live scenario previews for supported VoCore
  layouts.
- Improved CAS layouts for landscape, square, and round displays, including
  safer name placement, better scale-label spacing, a dedicated circular
  layout, and calibrated round rear and header groups.
- Updated the built-in guide and public documentation for the current capture,
  multi-area, idle-theme, vehicle-resolution, and CAS behaviour.

## 1.1.0 - 2026-07-23

- Made the capture-area editor toolbar draggable and able to move itself away
  when it overlaps or approaches the area being edited.
- Kept every screen's Enabled toggle visible in narrow SimHub windows and added
  horizontal scrolling as a fallback for the fixed-width settings layout.
- Prevented the CAS overlay, including its DIST and RTG scales, from appearing
  over idle clocks or themes while the game is paused, in menus, or waiting for
  a valid car.
- Linked the built-in purchase action to the DashDeck Ko-fi product page.

## 1.0.0 - 2026-07-23

- Initial public release of DashDeck.
- Added the Invisible dash and three independently configurable mirror screens.
- Added VoCore, secondary monitor, phone/tablet, and OBS browser-source output.
- Added per-car area profiles, tilted captures, and round VoCore support.
- Added the CAS rear-proximity overlay.
- Added the VoCore web browser, YouTube/Twitch player, and virtual touchpad.
- Added customizable idle screens and SimHub Control Mapper actions.
- Added online trial, lifetime license activation, automatic update checks, and
  the standalone DashDeck installer.
