# DashDeck Guide

DashDeck can restore information hidden behind a physical cockpit display or
move an in-game screen onto a dedicated device. This document covers the basic
workflow; the Guide tab inside the plugin contains the complete reference.

## Screen Types

### Invisible dash

Use the Invisible dash when a physical DDU overlaps the main monitor. Select
the area hidden by the device and DashDeck shows that same area on the physical
display, creating a see-through effect.

The Invisible dash configuration is global and can optionally show only in
menus and replay.

### Mirror screens

Use Screen 1, Screen 2, or Screen 3 for an in-game mirror, dashboard, camera
view, or instrument. The capture area and source monitor are stored per car,
because the position of an in-game display can change between cars.

Each Screen can have one, two, or three capture areas. The number of areas is
global for that Screen, while each area's coordinates, tilt, and source monitor
are saved for the current car. Use the Next and Previous capture area controls
to switch between them while driving; the selection wraps from the last area
back to the first and in the opposite direction.

For Le Mans Ultimate and rFactor 2, DashDeck resolves the real vehicle model so
different teams and liveries of the same model can share one capture profile.
The resolver retries when the game's vehicle API is not ready yet and can reuse
its cached vehicle list instead of permanently falling back to a team name.

## Creating a Capture

1. Enable the required screen.
2. Select its source monitor.
3. For Screen 1, 2, or 3, add a second or third area only if it is needed and
   select the area to configure.
4. Choose **Edit area on screen**.
5. Drag and resize the selection over the required part of the simulator.
6. If the in-game display is angled, use the tilt handle to align the
   selection.
7. Select the output device and choose the scaling mode.

The number of areas can be changed without a car loaded. Area coordinates
remain visible in the UI, but per-car geometry can only be edited after SimHub
has identified the current car. Removing an area asks for confirmation.

The area editor toolbar can be dragged to a convenient position and
automatically moves away when it would cover the area being edited.

The global Control Mapper action opens the editor on the Invisible dash. Use
the Screen/area selector inside the editor to move to another configured area.
Areas on the same source monitor reuse the frozen image; selecting an area on
another monitor captures only that monitor. Opening the editor directly from a
Screen starts on that Screen's active area.

Best quality is obtained when the capture area has the same aspect ratio and a
similar resolution to the output device.

## Outputs

### VoCore

DashDeck temporarily uses its own dashboard while the screen is active. When
the screen is disabled, the VoCore returns to the dashboard selected in the
screen settings.

Rectangular VoCore displays can also show the DashDeck web browser and video
player. Round VoCore displays automatically use a circular capture and do not
offer web or video output.

### Secondary monitor

The capture is displayed full screen on the selected secondary monitor. The
same monitor cannot be used as both a capture source and an output because that
would create a recursive image.

### Phone, tablet, and OBS

DashDeck provides a browser URL for each remote output. Use the local URL in an
OBS browser source, or enable network viewing and scan the QR code to open the
output on a phone or tablet.

Choose **Native** to stream the capture at its original pixel size with the
lowest CPU and network use. **HD** and **Full HD** resize the capture on the
helper GPU before JPEG encoding, which avoids asking a high-DPI phone or OBS to
magnify a small compressed frame. When HD or Full HD is selected, choose
**High quality** for a natural image or **Sharp** for an additional sharpening
pass. The selected long edge preserves the capture area's aspect ratio.

On a phone or tablet, tap the capture once when the keep-awake message appears.
DashDeck uses the browser's Screen Wake Lock API when it is available and a
silent-video compatibility fallback on normal HTTP LAN connections. The page
tries to restore the keep-awake state when it returns from the background.

Remote display access is view-only and uses a generated access token.

## CAS Overlay

The optional CAS overlay adds rear proximity information over a mirror capture.
It can show a rear chevron, side alerts, distance, time gap, session
information, and driver names. Enable it per mirror screen and configure its
shared appearance on the **CAS Overlay** tab.

The rear chevrons, distance label, driver names, session/lap text, scale text,
and spotter alerts can be resized independently. The spotter can use filled
arrows, outline arrows, or side chevrons. Safe, warning, critical, spotter,
primary text, secondary text, scale, and scale-label colours can all be changed,
and presets provide useful starting points.

The preview offers representative scenarios and the supported landscape,
square, and round VoCore resolutions. Round output uses a dedicated circular
safe layout. Portrait VoCore models remain available for idle-theme previews,
but are intentionally omitted from the CAS preview because the two side scales
and centre alert need horizontal space.

CAS is a driving aid and is only shown while the game is actively running with
a valid car. It is hidden in menus, while paused, and over idle clocks or
themes.

## Web Browser and Video

A rectangular VoCore can display a touch-controlled web browser with favorites,
an on-screen keyboard, and shared Windows clipboard support. Supported YouTube
and Twitch pages can be opened in a dedicated full-screen player with touch
controls.

The source can be switched between capture, browser, and video from the VoCore
or through SimHub Control Mapper.

## Virtual Touchpad

The **Touchpad** tab turns one or more VoCore displays into a Windows trackpad.
It supports pointer movement, left and right click, drag, scrolling, and pinch
zoom. It can appear automatically in game menus and close when driving begins.

## Idle Screens

Mirror screens show an idle screen when there is no active car to capture.
DashDeck includes a clock and supports custom themes containing:

- a photo or animated GIF;
- a short MP4 or WEBM video;
- time and date;
- driver name and number; and
- a country flag.

Create themes on the **Idle themes** tab and select one for each mirror screen.
The preview can emulate the supported VoCore models and orientations, including
square and round displays. Themes render from the target's real pixel size, so
Windows display scaling on any desktop monitor does not make their contents
larger or smaller on the output.

## Control Mapper

DashDeck registers SimHub Control Mapper actions for editing capture areas,
enabling or disabling individual screens, moving each Screen to its Next or
Previous configured capture area, switching between capture and web sources,
and toggling the virtual touchpad.

These actions can be assigned to steering-wheel buttons, button boxes, or other
controllers supported by SimHub.

## Troubleshooting

- Update SimHub before diagnosing capture or device problems.
- Confirm that the selected source monitor and output device are still
  connected.
- Make sure `DashDeck.dll` is installed in the SimHub root folder, not in
  `SimHub\Plugins`.
- If DashDeck reports that the .NET 10 Runtime (x64) is missing, use the
  built-in Install action. DashDeck downloads Microsoft's official installer
  and restarts SimHub automatically after a successful installation.
- For phone or tablet output, allow SimHub through the Windows firewall when
  prompted and keep both devices on the same network.
- Enable debug logging on the **Advanced** tab only while diagnosing a problem.
  Logs can be opened directly from that tab.

For detailed explanations of every option, open the built-in **Guide** tab.
