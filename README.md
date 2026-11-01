# MGU Store apps: Gentleman Function and Exhaust & Start/Stop

Two iDrive 7 (MGU) apps, published for the [MGU Store](https://github.com/robertnisipeanu/mgu-store)
in its **Releases** layout: each release carries the built OAP packages (`<id>@<version>.tgz`, without
BMW's oap-sdk, which the head unit provides) and `mgu-store.json` with the titles and icons.

| App | Id | Version | What it does |
|---|---|---|---|
| Gentleman Function | `gentleman` | 2.0.0 | Moves the passenger seat (seat module 0x6E) on one simple page: make room for the rear passenger and return, adjust (forward/back, up/down, backrest), two memories |
| Exhaust & Start/Stop | `exhaust_flap` | 1.3.5 | Exhaust flap and auto start/stop control |

## Install with the Store

In the Store on the car: add a source, GitHub, this repository, and pick **Releases**. Both apps then show
in the list.

Notes:

- If the same apps were installed earlier with the iDrive7 Apps Installer, remove them first, or the Store
  installs these beside them under another id.

## New version

Build with idrive7-apps (`python kit/tools/build.py gentleman exhaust_flap`), take
`node_modules/oap-sdk` out of each `dist/<id>@<version>.tgz`, and attach the packages, the icons and
`mgu-store.json` to a new GitHub release.

## Licence

MIT (see LICENSE). Built on the kit of [idrive7-apps](https://github.com/cauliflowermossgrape/idrive7-apps)
(MIT, Copyright (c) 2026 cauliflowermossgrape).
