# Changelog

## 1.6.0 - 2026-07-28

- Made CAS On/Off configurable independently for every logical capture area,
  shared across all cars and editable without loading a car.
- Reorganized the Screens tab into clearly separated settings groups labelled
  ALL CARS, CURRENT CAR, THIS DEVICE, or WAITING FOR CAR, so every option's
  scope is visible where it is edited.
- Kept the selected capture area stable when changing CAS or switching between
  Capture and Web, preventing the area selector from becoming empty.
- Improved the Invisible dash layout with boxed Placement and Image processing
  sections while keeping its already-global scope free of redundant labels.
- Prevented stale custom idle-theme frames from flashing over a live VoCore
  after upgrades, state changes, or output-session replacement.
- Debounced transient SimHub presentation-state samples and made ownership
  deterministic when legacy settings assign multiple Screens to one VoCore.
- Updated the public and built-in guides with the new screen-setting scopes,
  per-area CAS workflow, and current UI group names.

## 1.5.0 - 2026-07-27

- Added ready-made controller integrations for Elgato Stream Deck and Stream
  Deck +, Stream Dock, and Ulanzi Studio through the shared SimHub Control
  Bridge.
- Added controller actions for screen power, area editing, exact area
  selection, previous/next or knob-driven area cycling, Capture/Web switching,
  and touchpad visibility and power.
- Kept controller titles, icons, selected screens, capture areas, and live
  button states synchronized with the real DashDeck state.
- Added controller component installation and update management to the
  Controllers tab, including installed/available versions and safe application
  restart handling.
- Removed Logitech / Loupedeck from the DashDeck plugin because its action
  model cannot configure per-action icons consistently with the other
  supported controller applications.
- Prevented a current or previously used VoCore from briefly showing a capture
  frame while a Screen or Invisible dash toggle is being reconciled.
- Added a non-modal client-messages window with ordered messages, unread
  navigation, and persistent read history.
- Expanded the public and built-in guides with controller installation,
  actions, knob support, live-state behavior, and troubleshooting.

## 1.4.1 - 2026-07-26

- Fixed Stream Dock integration updates leaving the controller application closed. DashDeck now
  resolves the installed executable when process inspection is unavailable, restores the official
  working directory when launching it, and verifies that the application restarted successfully.
- Changed controller integration checks to ignore residual plugin and configuration files when the
  corresponding Stream Deck, Stream Dock, Ulanzi, or Logitech / Loupedeck software is not installed.
- Revalidate controller applications immediately before installation so software removed after an
  update check cannot trigger downloads, installers, or Windows file-association prompts.

## 1.4.0 - 2026-07-25

- Renamed the browser output to Phone / Tablet / OBS and added Native, HD, and
  Full HD stream resolutions.
- Added real GPU resize quality controls for HD and Full HD streams, applying
  high-quality or sharpened reconstruction before JPEG encoding.
- Clarified that the global JPEG stream quality applies to both VoCore and
  Phone / Tablet / OBS outputs.
- Made area changes deterministic on static desktops by forcing a current
  helper frame, rebuilding only the affected monitor duplication when needed,
  and using a bounded helper-restart fallback.
- Unified idle/live transitions across VoCore, monitor, and browser outputs so
  each keeps a current live frame at 1 FPS and resumes without stale idle or
  previous-area content.
- Added transition and control-refresh diagnostics for game state, output
  state, capture dimensions, and first-frame latency.
- Kept source-monitor identity stable across Windows display renumbering and
  Surround/Eyefinity topology changes, with the UI, runtime, and helper now
  resolving the same current monitor from saved bounds and hardware identity.
- Made the capture-area selector deterministic while car profiles are rebuilt
  and added monitor-topology, resolved-source, and selected-area diagnostics.
- Kept phone and tablet screens awake while displaying a remote capture: the
  page uses the official Screen Wake Lock API when available and activates a
  silent-video fallback after the first tap on HTTP LAN connections.
- Kept the Windows cursor at a consistent apparent size on phone, tablet, and
  OBS outputs when switching between Native, HD, and Full HD stream resolutions.

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
