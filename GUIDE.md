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

For Le Mans Ultimate and rFactor 2, DashDeck resolves the real vehicle model so
different teams and liveries of the same model can share one capture profile.

## Creating a Capture

1. Enable the required screen.
2. Select its source monitor.
3. Choose **Edit area on screen**.
4. Drag and resize the selection over the required part of the simulator.
5. If the in-game display is angled, use the tilt handle to align the
   selection.
6. Select the output device and choose the scaling mode.

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

Remote display access is view-only and uses a generated access token.

## CAS Overlay

The optional CAS overlay adds rear proximity information over a mirror capture.
It can show a rear chevron, side alerts, distance, time gap, session
information, and driver names. Enable it per mirror screen and configure its
shared appearance on the **CAS Overlay** tab.

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

## Control Mapper

DashDeck registers SimHub Control Mapper actions for editing capture areas,
enabling or disabling individual screens, switching between capture and web
sources, and toggling the virtual touchpad.

These actions can be assigned to steering-wheel buttons, button boxes, or other
controllers supported by SimHub.

## Troubleshooting

- Update SimHub before diagnosing capture or device problems.
- Confirm that the selected source monitor and output device are still
  connected.
- Make sure `DashDeck.dll` is installed in the SimHub root folder, not in
  `SimHub\Plugins`.
- Install the .NET 8 Desktop Runtime if DashDeck reports that the capture helper
  cannot start.
- For phone or tablet output, allow SimHub through the Windows firewall when
  prompted and keep both devices on the same network.
- Enable debug logging on the **Advanced** tab only while diagnosing a problem.
  Logs can be opened directly from that tab.

For detailed explanations of every option, open the built-in **Guide** tab.
