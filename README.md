# BrainCircuit

An installable, offline capable electronic circuit simulator web app.
Draw a circuit, run a real time simulation, watch the oscilloscope - on a
phone, tablet, desktop PC, Android, iOS, Windows, macOS or Linux.

**Installable:** open the site once and it can be installed as an app
(install prompt with an Install / No choice). After the first load it keeps
working with no internet connection.

---

**Live On** [BrainCircuit](https://braincircuit.puter.site)
<br>
OR
<br>
**Deploy:** upload the folder to any static HTTPS host
(GitHub Pages, Netlify, Vercel, your own server, ...).

## Files that make the app work

| File | Purpose |
|------|---------|
| `index.html` | The whole app shell in one file: branding, install prompt, offline screen, PWA logic, styles |
| `manifest.json` | Web app manifest (name, icons, colours, standalone display) |
| `service-worker.js` | Caches every file so the app runs fully offline |
| `braincircuit_logo.png` | App logo (also used for icons, favicon, About box, install dialog) |
| `circuitjs1/` | The compiled simulator engine + example circuits |
| `src/`, `war/`, `build.gradle` | Java/GWT sources and build files of the simulator |

## Rebuild from source

Requirements: JDK 8 and the included Gradle wrapper.

## PWA behaviour

* **Install prompt** - BrainCircuit shows its own dialog with an **Install** and a **No** button. Choosing *No*
  stores the decision and the app never auto-asks again (an *Install* button
  stays available in the About box).
* **Offline** - the service worker pre-caches the app. The "You are offline"
  screen is only shown while the simulator has not finished loading yet; once
  the app is running, losing the internet never shows a warning and the
  simulator keeps working.
* **Any device** - responsive layout, touch support, installable on
  Android / iOS / Windows / macOS / Linux.

## Keyboard shortcuts

Most of the original simulator shortcuts still apply, for example:
`Esc` finish drawing, `Del` delete element, `Ctrl+Z` undo, `Ctrl+S` save,
`Space` run/stop, `+`/`-` zoom, `?` for the full list (Help menu).
