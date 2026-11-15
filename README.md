# IgaraPost
IgaraPost is an environmental social network by Vento Norte UEA for NASA Space Apps. It connects Amazon communities' geolocated reports of smoke, fires and floods with satellite data, interactive maps and experimental NISAR image comparisons, making Earth observation more accessible and supporting citizen science.
<div align="center">

<img src="app/public/igarapost-logo.png" alt="IgaraPost logo" width="120" />

# Credits and Acknowledgments

**IgaraPost** · **Vento Norte UEA** Team · NASA Space Apps Challenge 2026 · *Dancing with the SARs* challenge

</div>

---

IgaraPost was created by the Vento Norte team from the State University of Amazonas (Universidade do Estado do Amazonas, UEA). To get here, we relied on open-source libraries, open data from space and scientific agencies, and third-party services. This page acknowledges each of them and makes clear what was developed by the team.

## Table of Contents

- [Developed by the Vento Norte team](#developed-by-the-vento-norte-team)
- [Data and services](#data-and-services)
- [Libraries included in the app](#libraries-included-in-the-app)
- [Development tools](#development-tools)
- [Data processing in Python](#data-processing-in-python)
- [Typography, icons and images](#typography-icons-and-images)
- [Use of artificial intelligence](#use-of-artificial-intelligence)

---

## Developed by the Vento Norte team

The code, screens, texts and artwork listed below were created for IgaraPost and have no external authorship. They use the libraries listed in the following sections, but the logic, design and content belong to the team.

| Part | What it includes |
|---|---|
| **App** (`app/src/`) | All screens (Feed, Map, Report, Profile, NISAR Explorer, How to use, About), components, on-device storage, sync queue and the Supabase connection |
| **SARS provider** (`app/src/sars/`) | Global layers, real-time data, regions and the "off the radar" check for reports |
| **Translation** (`app/src/i18n/`) | Language system and interface dictionaries |
| **Database** (`supabase/`) | Tables, security rules (RLS), triggers, photos and moderation |
| **Server** (`server/`) | Server used up to version 8, written in plain Node.js, plus `Dockerfile` and `render.yaml` |
| **Data pipeline** (`data-pipeline/`) | Scripts that download, clip and process data from INPE, Cemaden, OpenStreetMap and NISAR |
| **Tests** (`app/tests/`) | End-to-end tests, simulated Supabase and language tests |
| **Android** (`app/android/`) | Customization of the Capacitor-generated project: package, versions, signing, icons and splash screens |
| **Visual identity** | IgaraPost logo, Vento Norte UEA logo, app icons, team photo and the "Other" background artwork |
| **Documentation** | `README.md` and the `docs/` folder |

---

## Data and services

IgaraPost only exists thanks to open data. We thank the institutions that maintain it.

| Source | Maintainer | Use in IgaraPost |
|---|---|---|
| [NASA GIBS](https://earthdata.nasa.gov/gibs) | NASA EOSDIS / ESDIS | Smoke (MODIS AOD), flood (MODIS Flood), daily imagery (VIIRS) layers and the **Blue Marble Next Generation** basemap |
| [NASA FIRMS](https://firms.modaps.eosdis.nasa.gov/) | NASA LANCE | Active fire detections (VIIRS NOAA-20 and Suomi NPP) |
| [OPERA DSWx-S1](https://www.jpl.nasa.gov/go/opera) | NASA/JPL | Surface water detected by radar. *Contains modified Copernicus Sentinel data (ESA).* |
| [NISAR](https://science.nasa.gov/mission/nisar/), via [ASF DAAC](https://search.asf.alaska.edu/) | NASA/JPL and ISRO | NISAR Explorer around Manaus |
| [Programa Queimadas](https://data.inpe.br/queimadas/dados-abertos/) | INPE | Fire hotspots in Brazil and real-time updates |
| [Alerta Secas](https://alertasecas.cemaden.gov.br/) | Cemaden/MCTI | Municipal boundaries |
| [OpenStreetMap](https://www.openstreetmap.org/copyright) | © OpenStreetMap contributors (ODbL) | Street map, places, rivers and roads |
| [MyMemory](https://mymemory.translated.net/) | Translated srl | Automatic translation of reports |
| [Supabase](https://supabase.com/) | Supabase Inc. | Accounts, reports, comments, photos and moderation |
| [Google Maps Platform](https://developers.google.com/maps) *(optional)* | Google | "Google Satellite" and "Google Map" basemaps, when an API key is configured |

---

## Libraries included in the app

These libraries are bundled in the APK. All of them are open source, and copyright notices follow each one's license.

| Library | Version | Authors | License |
|---|---|---|---|
| [React](https://react.dev/) and React DOM | 18.3.1 | Meta Platforms, Inc. and contributors | MIT |
| [Leaflet](https://leafletjs.com/) | 1.9.4 | Volodymyr Agafonkin and contributors | BSD-2-Clause |
| [Capacitor](https://capacitorjs.com/) (core and android) | 6.2.0 | Ionic and contributors | MIT |
| [Apache Cordova Android](https://cordova.apache.org/) | 10.1.1 | Apache Software Foundation | Apache 2.0 |
| [AndroidX / Jetpack](https://developer.android.com/jetpack/androidx) | various | Google / Android Open Source Project | Apache 2.0 |
| [Kotlin](https://kotlinlang.org/) and [kotlinx.coroutines](https://github.com/Kotlin/kotlinx.coroutines) | 1.6.4 (coroutines) | JetBrains and contributors | Apache 2.0 |

<details>
<summary><b>Included AndroidX modules</b></summary>

<br>

| Module | Version |
|---|---|
| appcompat · appcompat-resources | 1.6.1 |
| core · core-ktx | 1.12.0 |
| core-splashscreen | 1.0.1 |
| coordinatorlayout | 1.2.0 |
| activity | 1.8.0 |
| fragment | 1.6.2 |
| webkit | 1.9.0 |
| emoji2 · emoji2-views-helper | 1.2.0 |
| savedstate | 1.2.1 |
| startup-runtime | 1.1.1 |
| profileinstaller | 1.3.0 |
| annotation-experimental | 1.3.0 |
| lifecycle, arch-core, loader, viewpager, drawerlayout, customview, cursoradapter, interpolator, vectordrawable, versionedparcelable, tracing | AndroidX dependencies |

</details>

---

## Development tools

These tools were used to build and test the project and are not bundled in the APK.

| Tool | Authors | License |
|---|---|---|
| [Vite](https://vitejs.dev/) 5.4, with [esbuild](https://esbuild.github.io/) and [Rollup](https://rollupjs.org/) | Evan You, Evan Wallace, Rich Harris and contributors | MIT |
| [TypeScript](https://www.typescriptlang.org/) 5.5 | Microsoft | Apache 2.0 |
| [DefinitelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) (`@types/react`, `@types/leaflet`) | Community | MIT |
| [Capacitor CLI](https://capacitorjs.com/) 6.2 | Ionic | MIT |
| [Gradle](https://gradle.org/) and [Android Gradle Plugin](https://developer.android.com/build) 8.2 | Gradle Inc. and Google | Apache 2.0 |
| [Playwright](https://playwright.dev/) | Microsoft | Apache 2.0 |
| [tsx](https://github.com/privatenumber/tsx) | Hiroki Osame and contributors | MIT |
| [Node.js](https://nodejs.org/) 22 | OpenJS Foundation | MIT |
| [PostgreSQL](https://www.postgresql.org/) (via Supabase) | PostgreSQL Global Development Group | PostgreSQL License |

---

## Data processing in Python

Libraries used in `data-pipeline/` to download and prepare the satellite data.

| Library | Authors | License |
|---|---|---|
| [NumPy](https://numpy.org/) | NumPy Developers | BSD-3-Clause |
| [SciPy](https://scipy.org/) | SciPy Developers | BSD-3-Clause |
| [Pillow](https://python-pillow.org/) | Jeffrey A. Clark and contributors | MIT-CMU |
| [h5py](https://www.h5py.org/) | Andrew Collette and contributors | BSD-3-Clause |
| [Rasterio](https://rasterio.readthedocs.io/) | Mapbox and contributors | BSD-3-Clause |
| [pyproj](https://pyproj4.github.io/pyproj/) | pyproj contributors | MIT |
| [Shapely](https://shapely.readthedocs.io/) | Sean Gillies and contributors | BSD-3-Clause |
| [earthaccess](https://earthaccess.readthedocs.io/) | NSIDC and the earthaccess community | MIT |

---

## Typography, icons and images

**Fonts**, loaded from [Google Fonts](https://fonts.google.com/), all under the SIL Open Font License 1.1:

- **Bricolage Grotesque**, by Mathieu Triay
- **Inter**, by Rasmus Andersson
- **IBM Plex Mono**, by IBM

**Icons:** drawn by the team in SVG. The bell icon comes from [Lucide](https://lucide.dev/) (ISC license).

**Post background images:**

| Image | Author |
|---|---|
| Wildfire (firefighter in a fire) | *[author and outlet to be confirmed]* |
| Smoke (Amazon Theatre covered in smoke) | *[author and outlet to be confirmed]* |
| Flood (flooded street in Manaus) | *[author and outlet to be confirmed]* |
| Other (IgaraPost artwork) | Vento Norte team |

**Offline basemap:** NASA Blue Marble Next Generation, via GIBS.

---

## Use of artificial intelligence

In accordance with the NASA Space Apps Challenge rules, we declare that IgaraPost was developed by the Vento Norte UEA team **with the assistance of the AI Claude (Anthropic)** in reviewing and testing the code. The coding, design decisions, visual identity and final validation were done by the team.

---

<div align="center">

Made in Manaus, Amazonas, by the **Vento Norte Team · UEA**

</div>
