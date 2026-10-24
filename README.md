# Aster skin for Jellyfin

A CSS theme that makes Jellyfin's web interface look like the [Aster](https://github.com/AsterMediaPlayer/aster-media-player) app: near-black backgrounds, the system font, white focus, rounded cards, a full-screen title page with pill buttons, round cast photos, and a rounded TV guide.

Aster and this skin aren't affiliated with or endorsed by the Jellyfin project.

## Install

Paste this line into **Dashboard ▸ General ▸ Branding ▸ Custom CSS** (everyone on the server) or **User Settings ▸ Display ▸ Custom CSS** (just you):

```css
@import url("https://cdn.jsdelivr.net/gh/AsterMediaPlayer/aster-skin@main/aster.css");
```

Then reload the page. It works with any of Jellyfin's built-in themes, but looks as intended with **Dark**.

jsDelivr caches files from a branch for a while, so a change pushed here can take some time to reach you. Once there are tagged releases, pin one instead of `@main` (for example `aster-skin@v0.1.0`) so an update never changes your server's look by surprise.

## What it covers

| Area | Change |
| --- | --- |
| Colours | Near-black background, white accent (focus, progress, selection) |
| Type | The system font: San Francisco on Apple devices, Segoe UI on Windows, Roboto on Android |
| Header | Dark glass bar |
| Tabs | Pill-shaped segmented control |
| Cards | Rounder corners, a lift on hover |
| Title page (desktop and TV) | Full-screen backdrop, no poster, large title, a row of pill buttons with Play / Resume spelled out |
| Cast & Crew | Round photos |
| Live TV guide | Rounded cells with gaps, white focus, no category colours |

Phones keep Jellyfin's own title-page layout.

## What it can't do

CSS restyles what's there; it can't add what isn't. These parts of Aster need JavaScript and are planned as a separate script:

- The Home screen's full-screen hero (artwork, logo, "Resume · 21 min left", page dots)
- Watch OP / Watch ED and the theme song cards
- Playlist channels and their schedule

It also only reaches the web interface (and apps that show it, such as Jellyfin Media Player). Jellyfin's native TV and phone apps, and Aster itself, aren't affected.

## Compatibility

Written against **jellyfin-web v12.1**. Jellyfin's class names change between releases, so a server update can undo parts of the look; each section of `aster.css` names the Jellyfin markup it targets, to make fixes quick.

## Customising

The variables at the top of `aster.css` set the look. To change them without copying the file, add your own block **after** the `@import` line, for example:

```css
:root[data-theme] {
    --aster-radius: 6px;
    --aster-bg: #000;
}
```
