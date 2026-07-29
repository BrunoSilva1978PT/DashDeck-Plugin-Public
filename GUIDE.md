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

Each Screen can have one, two, or three capture areas. The number of areas and
each logical area's CAS On/Off state are global for that Screen, while the
coordinates, tilt, and source monitor are saved for the current car. Use the
Next and Previous capture area controls to switch between them while driving;
the selection wraps from the last area back to the first and in the opposite
direction. The selected area's CAS state is applied immediately when the area
changes.

The Screens tab labels every settings group with its scope:

- **ALL CARS** means the setting is shared by every car. This includes what the
  Screen shows, area slots and each area's CAS state, output and idle behaviour,
  and image processing.
- **CURRENT CAR** means the setting belongs to the loaded car. This applies to
  the selected area's source monitor, coordinates, and tilt. Without a loaded
  car, Area position shows **WAITING FOR CAR**: the monitor selection becomes
  the default for new car profiles, while coordinates and tilt remain
  read-only.
- **THIS DEVICE** means the setting belongs to the selected output device. The
  dashboard restored when a Screen is switched off is stored for that VoCore,
  not for a car or capture area.

The area selector always refers to the same global logical slot. For example,
**Area 2** can have CAS enabled for every car while each car keeps a different
source monitor, rectangle and tilt for Area 2. The Area position heading, source
monitor label and coordinates label show the selected area explicitly so it is
clear which per-car geometry is being edited.

The Invisible dash is already fully global, including its physical Placement,
so its sections do not repeat an **ALL CARS** label.

For Le Mans Ultimate and rFactor 2, DashDeck resolves the real vehicle model so
different teams and liveries of the same model can share one capture profile.
The team or livery identifier is only lookup evidence and never becomes the
profile name. DashDeck ignores short empty or changing telemetry samples, keeps
the last valid profile while the game API is unavailable, and revalidates saved
identifier mappings after startup so a game update cannot silently select an
old profile. A car profile is also locked throughout uninterrupted live
driving. DashDeck only considers a different car after Pause, Waiting for data,
menu or another session transition, then requires the new identity to remain
stable before resolving it.

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

The settings are grouped as **What this screen shows**, **Area slots & CAS**,
**Area position**, **Output & idle behaviour**, **Placement**, **Image
processing**, and **Dashboard when this screen is off**. The scope label beside
each heading shows whether a change affects every car, only the loaded car, or
the selected device.

The number of areas and each area's CAS On/Off state can be configured without
a car loaded. Area coordinates remain visible in the UI, but per-car geometry
can only be edited after SimHub has identified the current car. Removing an
area asks for confirmation.

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
information, and driver names. Select a Screen's capture area and enable CAS
separately for that logical area. The choice is global for every car and can be
configured without a car loaded. This lets one area be a mirror with CAS while
another area on the same Screen remains a clean dashboard or camera view.
Configure the shared colours, sizes, and visible details on the **CAS Overlay**
tab. CAS is not available on the Invisible dash or a web source.

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

## Controller Integrations

The **Controllers** tab can install the shared DashDeck Control Bridge and the
ready-made integration for controller software already installed on the PC:

- Elgato Stream Deck and Stream Deck +;
- Stream Dock (experimental);
- Ulanzi Studio (experimental).

Select **Check now**, then **Install / Update**. The first installation asks for
confirmation. An update that replaces the shared Control Bridge also asks
before restarting SimHub; later controller-only updates are applied
automatically where the controller software supports it. DashDeck ignores
packages for controller applications that are not installed.

After installation, open the controller application's action list or
marketplace and add the DashDeck actions to the required buttons or supported
knobs. The integration provides actions to:

- enable or disable any of the four screens;
- open a screen's capture-area editor;
- select an exact capture area;
- move to the previous or next area, or cycle areas with a supported knob;
- switch a compatible rectangular VoCore between Capture and Web;
- show or hide the virtual touchpad; and
- enable or disable the touchpad.

Button titles, icons, selected screens, available capture areas, and live state
are supplied by DashDeck. A toggle becomes active only when its real plugin
state matches that button: for example, an exact-area button is active only
while that same Screen and area are selected. Screen and area changes made in
the plugin, SimHub, or a controller are synchronized automatically.

The **Connection** section shows the live connection and installed version for
the bridge and each supported controller plugin. If an integration is
installed but not connected, confirm that its controller application is
running, then use **Check now** to verify that all installed components are up
to date.

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
- If a controller integration is not connected, make sure its controller
  software is running and check its status and version on the **Controllers**
  tab. Only install integrations for controller software present on the PC.
- Enable debug logging on the **Advanced** tab only while diagnosing a problem.
  Logs can be opened directly from that tab. DashDeck always keeps identity and
  profile transitions in a compact `identity-audit.log`; it survives restarts,
  rotates at 1 MB and keeps only one `identity-audit.old.log` backup. The normal
  `plugin.log` still starts clean with every SimHub session.

For detailed explanations of every option, open the built-in **Guide** tab.
