# MGU Store apps: Gentleman Function, Exhaust & Start/Stop, Shift Lights

Three iDrive 7 (MGU) apps, published for the [MGU Store](https://github.com/robertnisipeanu/mgu-store)
in its **Releases** layout: each release carries the built OAP packages (`<id>@<version>.tgz`, without
BMW's oap-sdk, which the head unit provides) and `mgu-store.json` with the titles and icons.

| App | Id | Version | What it does |
|---|---|---|---|
| Gentleman Function | `gentleman` | 2.1.0 | Moves the passenger seat (seat module 0x6E) on one simple page: make room for the rear passenger and return, adjust (forward/back, up/down, backrest), two memories |
| Exhaust & Start/Stop | `exhaust_flap` | 1.4.0 | Exhaust flap and auto start/stop control; starts with the head unit, so start/stop stays off without opening the app |
| Shift Lights | `shift_lights` | 1.6.0 | BMW M-style shift lights at the top centre of the instrument cluster: 6 yellow and 4 red strips per side lighting from the ends in, the whole bar red and flashing at the shift point; works in every cluster view, Map view included; move it and resize it from the app; starts with the head unit |

## Install with the Store

In the Store on the car: add a source, GitHub, this repository, and pick **Releases**. The apps then show
in the list.

Notes:

- **Shift Lights needs the Cluster renderer** (`cluster-render`), the service that draws apps' content on
  the cluster: add the source `robertnisipeanu/idrive-apps` in the Store and install "Cluster renderer".
- **Starting with the head unit** (Exhaust & Start/Stop, Shift Lights) is set by the iDrive7 Apps
  Installer, which writes `"-appStartType": "autostart"` for apps whose app.json has `"autostart": true`.
  Installed by the Store, they may only start when opened.
- If the same apps were installed earlier with the iDrive7 Apps Installer, remove them first, or the Store
  installs these beside them under another id.

## New version

Build with idrive7-apps (`python kit/tools/build.py gentleman exhaust_flap shift_lights`), take
`node_modules/oap-sdk` out of each `dist/<id>@<version>.tgz`, and attach the packages, the icons and
`mgu-store.json` to a new GitHub release.

## Licence

MIT (see LICENSE). Built on the kit of [idrive7-apps](https://github.com/cauliflowermossgrape/idrive7-apps)
(MIT, Copyright (c) 2026 cauliflowermossgrape).

Shift Lights includes `cluster_render_client.js` from
[robertnisipeanu/idrive-apps](https://github.com/robertnisipeanu/idrive-apps/tree/main/native/cluster-render)
(Copyright (C) 2026 Robert Nisipeanu) unchanged, under the Mozilla Public License 2.0; its source is in that
repository.
