# Awesome Offline Knowledge [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of content, tools, and infrastructure for keeping knowledge accessible without the internet — for disasters, shutdowns, remote regions, classrooms, and the long term.

**Scope.** This list is about *offline access to knowledge*: openly licensed content you can store locally, tools to read, serve, and capture it, and the ways it travels without a network. It completes a triangle with two sibling lists, both under *Other Related Lists* below: **awesome-decentralized-web** (who controls the infrastructure) and **awesome-resilient-communication** (how people communicate when infrastructure fails).

**Out of scope:**
- Pirated or unlicensed content. Everything listed is public domain, openly licensed, or free to download and redistribute offline for noncommercial use — and any entry whose license restricts commercial use or redistribution states the restriction in its description.
- Cryptocurrency- and token-dependent projects.
- AI tools and agent frameworks.
- General self-hosting software without an offline-first purpose.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a project.

**How to read this list.** Three different things get called "offline knowledge", and you usually need all three:

- **Content** — the knowledge itself, in bulk and openly licensed. *(Wikimedia dumps, Project Gutenberg, OpenStreetMap)*
- **Tools** — readers, servers, and capture software that make content usable off the network. *(Kiwix, Calibre, ArchiveBox)*
- **Transport** — how content moves without connectivity: hotspots, removable media, sneakernets. *(Internet-in-a-Box, NNCP)*

Entries marked **Dormant** still work but their source repository has had no activity for over 2 years — the tag states the measured date. Dead projects live in the Graveyard section at the bottom.

## Contents

- [Prepare Before You Need It](#prepare-before-you-need-it)
- [Choose by Scenario](#choose-by-scenario)
- [Deployment at a Glance](#deployment-at-a-glance)
- [Content Collections](#content-collections)
  - [General Reference](#general-reference)
  - [Health and Medicine](#health-and-medicine)
  - [Education and Learning](#education-and-learning)
  - [Books and Languages](#books-and-languages)
  - [Technical and Practical Knowledge](#technical-and-practical-knowledge)
- [Readers and Reference Tools](#readers-and-reference-tools)
- [Offline Servers and Learning Platforms](#offline-servers-and-learning-platforms)
- [Maps and Navigation](#maps-and-navigation)
- [Capture and Web Archiving](#capture-and-web-archiving)
- [Preservation, Packaging, and Verification](#preservation-packaging-and-verification)
- [Sneakernets and Offline Transfer](#sneakernets-and-offline-transfer)
- [Case Studies](#case-studies)
- [Guides and Communities](#guides-and-communities)
- [Graveyard](#graveyard)
- [Other Related Lists](#other-related-lists)
- [Contributors](#contributors)

## Prepare Before You Need It
Everything on this list works only if it was downloaded, installed, and tested while the network still worked. Preparation is unglamorous and takes an afternoon; the checklist is short:

- Download content and the applications that read it in advance, and check free storage before starting a multi-gigabyte archive.
- Test the complete setup with Wi-Fi and cellular disabled: first launch, opening content, search. Confirm nothing needs an online login, license activation, DNS lookup, cloud API, or one-time network setup.
- Keep at least two verified copies on different storage devices.
- Verify checksums or signatures where the source publishes them.
- Record each archive's version and date, and schedule periodic refreshes — quarterly is enough for most content.
- Store readers and installers alongside the content itself: an archive is useless if compatible software is not at hand for your platform.
- Keep short startup instructions, printed or as a plain text file on the same media, so someone other than you can bring the system up.
- Plan for power: charged devices, replaceable batteries or power banks, solar charging where outages may be long, and low-power servers such as a Raspberry Pi where a hub must stay running.
- If you run a community server, test it from several client devices over its own Wi-Fi, not only from the machine it runs on.
- Prefer formats that stay usable without a specific vendor or account — plain files outlive app-locked libraries.
- For medical and emergency material, note the edition date: offline references age, and none of them replace qualified professional help.

## Choose by Scenario
Reasonable starting combinations, drawn from the entries in the sections below — starting points, not guarantees, and the medical caveat above applies throughout.

|Scenario                                |Reasonable starting point                                                                                                        |
|----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
|Personal offline reference library      |Kiwix with ZIM archives from the Kiwix Library, Calibre for books, Zeal or DevDocs for programming documentation                 |
|Offline classroom                       |Kolibri or MoodleBox on a Raspberry Pi, with PhET simulations and OpenStax textbooks loaded in advance                           |
|Community knowledge hotspot             |Internet-in-a-Box or RACHEL serving Wikipedia ZIM archives, offline maps, and books over local Wi-Fi                             |
|Medical reference collection            |WikiMed plus Hesperian Health Guides, with edition dates recorded                                                                |
|Offline maps and navigation             |Organic Maps, CoMaps, or OsmAnd on phones; Geofabrik extracts and Protomaps for self-hosted maps                                 |
|Capturing websites before they disappear|ArchiveWeb.page or Browsertrix Crawler to capture, ReplayWeb.page to read the result, Zimit when the target format is a Kiwix ZIM|
|Long-term preservation                  |BagIt packaging with checksum manifests, Archivematica for a full workflow, guidance from digipres.org                           |
|Moving updates across an air gap        |NNCP or plain removable media, apt-offline for Debian-based systems, checksums verified on both sides                            |

## Deployment at a Glance
The entries most often deployed in bulk, compared on what matters when you provision hardware. Storage figures are approximate as of September 2026 and only grow — treat them as planning numbers and check current sizes before buying media.

|System                        |Archive format                             |Approx. storage                                                      |Update method                                   |Incremental updates                                                    |Licensing                                      |Platforms                                        |
|------------------------------|-------------------------------------------|---------------------------------------------------------------------|------------------------------------------------|-----------------------------------------------------------------------|-----------------------------------------------|-------------------------------------------------|
|Kiwix (ZIM archives)          |ZIM                                        |MBs per archive, up to ~100 GB for full English Wikipedia with images|Re-download the whole ZIM from the Kiwix Library|✗ whole-file replace                                                   |Reader GPLv3; content mostly CC BY-SA          |Windows, macOS, Linux, Android, iOS, Raspberry Pi|
|Wikimedia Dumps               |Compressed XML/SQL                         |~20 GB compressed for English Wikipedia article text                 |New full dumps roughly twice a month            |✗ full re-download in practice                                         |CC BY-SA / GFDL                                |Raw data — any                                   |
|Project Gutenberg             |EPUB, HTML, plain text                     |MBs per book; on the order of 1 TB for a full mirror                 |rsync or HTTP mirrors                           |✓ rsync transfers only changes                                         |Public domain (US)                             |Standard formats — any                           |
|OpenStreetMap data            |PBF (planet or regional extracts)          |~80 GB planet file; country extracts far smaller                     |Replication diffs, minutely to daily            |✓                                                                      |ODbL                                           |Raw data — any                                   |
|Organic Maps / CoMaps / OsmAnd|Per-region map files                       |Hundreds of MB per country                                           |In-app region downloads                         |◐ OsmAnd offers diff-based live updates; the others re-download regions|Apps open source; map data ODbL                |Android, iOS                                     |
|Kolibri                       |Kolibri content channels                   |GBs, varies by channel selection                                     |Peer-to-peer sync, USB import, or online        |✓ device-to-device sync built in                                       |Platform MIT; content licenses vary per channel|Windows, macOS, Linux, Android, Raspberry Pi     |
|Internet-in-a-Box             |Bundles ZIM, Kolibri channels, and OSM maps|64 GB card to 1 TB+ drive, per content selection                     |Admin console re-downloads packages             |✗ whole-package replace                                                |Open-source stack; content licenses vary       |Raspberry Pi, Linux                              |
|RACHEL                        |Preloaded module bundles                   |Sized to device, typically hundreds of GB                            |Module downloads or USB from World Possible     |✗                                                                      |Mixed open licenses per module                 |RACHEL devices, Raspberry Pi                     |

✓ supported · ◐ partial or configuration-dependent · ✗ updates mean re-downloading the whole archive

Two practical consequences: on slow or metered links, prefer the systems with incremental updates (rsync mirrors, OSM diffs, Kolibri sync) and treat whole-file systems like ZIM as things you refresh occasionally by sneakernet; and check content licenses separately from software licenses — redistributing a preloaded device is a redistribution of everything on it.

## Content Collections
*The knowledge itself: bulk-downloadable, with the license stated where it is not fully open.*

### General Reference
- [Kiwix Library](https://library.kiwix.org/) - Catalog of ready-made ZIM archives: all of Wikipedia, Stack Exchange, Project Gutenberg, medical references, and hundreds more.
- [Wikimedia Dumps](https://dumps.wikimedia.org/) - Complete database exports of Wikipedia and its sister projects (CC BY-SA), the raw material behind most offline encyclopedia tools.

### Health and Medicine
*Offline medical references age: record the edition date, and treat them as support for — never a replacement of — qualified professional care.*

- [Hesperian Health Guides](https://hesperian.org/) - Publisher of *Where There Is No Doctor* and other field-medicine guides written for places without professional care; digital editions are free to download under a custom open-copyright policy that restricts commercial use.
- [WikiMed](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Medicine/App) - Curated offline snapshot of Wikipedia's medical articles (CC BY-SA), maintained with WikiProject Medicine and distributed as a Kiwix ZIM and mobile app.

### Education and Learning
- [OpenStax](https://openstax.org/) - Peer-reviewed college textbooks free to download as PDF; licenses vary by title between CC BY and CC BY-NC-SA — the noncommercial titles are not fully open.
- [PhET Interactive Simulations](https://phet.colorado.edu/) - Math and science simulations from the University of Colorado Boulder (CC BY), downloadable individually or as a complete offline website installer.

### Books and Languages
- [LibriVox](https://librivox.org/) - Public-domain audiobooks read by volunteers, all downloadable for offline listening.
- [Project Gutenberg](https://www.gutenberg.org/) - More than 75,000 public-domain e-books, downloadable in bulk.
- [Standard Ebooks](https://standardebooks.org/) - Carefully typeset, open-licensed editions of public-domain e-books.
- [Tatoeba](https://tatoeba.org/) - Openly licensed database of millions of example sentences and their translations across hundreds of languages, downloadable in full.

### Technical and Practical Knowledge
- [Appropedia](https://www.appropedia.org/) - Wiki of appropriate technology, sustainability, and development knowledge, with offline exports available through Kiwix.
- [Software Heritage](https://www.softwareheritage.org/) - Universal archive of software source code, preserving hundreds of millions of projects for the long term.

## Readers and Reference Tools
*Software for using stored knowledge on your own device.*

- [Aard2](https://aarddict.org/) - Android dictionary and Wikipedia reader for slob-format offline archives.
- [Calibre](https://calibre-ebook.com/) - The standard tool for e-book library management, format conversion, and reading.
- [DevDocs](https://devdocs.io/) - Combined API documentation browser for hundreds of programming tools, installable for fully offline use.
- [GoldenDict-ng](https://github.com/xiaoyifang/goldendict-ng) - Feature-rich dictionary application supporting StarDict, Babylon, and many other offline dictionary formats.
- [Kiwix](https://kiwix.org/) - Reader and server for ZIM archives on desktop, mobile, and Raspberry Pi — the standard way to use Wikipedia offline.
- [KOReader](https://koreader.rocks/) - Document and e-book reader for e-ink devices, phones, and desktops.
- [Zeal](https://zealdocs.org/) - Offline documentation browser for developers, using Dash-format docsets.

## Offline Servers and Learning Platforms
*A box that serves knowledge to everyone nearby.*

- [Internet-in-a-Box](https://internet-in-a-box.io/) - Turns a Raspberry Pi into a local knowledge hotspot serving Wikipedia, maps, books, and lessons to nearby devices.
- [Kolibri](https://learningequality.org/kolibri/) - Offline-first learning platform that syncs curricula between devices without internet, by Learning Equality.
- [MoodleBox](https://moodlebox.net/) - Self-contained Moodle server on a Raspberry Pi that broadcasts its own Wi-Fi network, for courses and quizzes in classrooms without connectivity.
- [RACHEL](https://worldpossible.org/) - Preloaded offline education server used in schools and community centers without connectivity, by World Possible.

## Maps and Navigation

- [CoMaps](https://www.comaps.app/) - Community-governed offline maps and navigation app built on OpenStreetMap data, forked from Organic Maps.
- [Geofabrik Downloads](https://download.geofabrik.de/) - Daily updated OpenStreetMap extracts (ODbL) by continent, country, and region — the practical way to get map data at a downloadable size.
- [OpenStreetMap](https://www.openstreetmap.org/) - The openly licensed map of the world; its data extracts power every offline maps app on this list.
- [Organic Maps](https://organicmaps.app/) - Offline maps and navigation app built on OpenStreetMap data, with detailed hiking and cycling coverage.
- [OsmAnd](https://osmand.net/) - Highly configurable offline maps, navigation, and map-editing app built on OpenStreetMap data.
- [Protomaps](https://protomaps.com/) - Serves an entire planet of map tiles from one static file (PMTiles), making self-hosted offline maps practical.

## Capture and Web Archiving
*Make your own offline copies while the network is still up.*

- [ArchiveBox](https://archivebox.io/) - Self-hosted web archive that snapshots the pages you feed it into several durable formats.
- [ArchiveWeb.page](https://archiveweb.page/) - Browser extension and desktop app by Webrecorder that records the pages you browse into portable WACZ archives, entirely on your own machine.
- [Browsertrix Crawler](https://github.com/webrecorder/browsertrix-crawler) - Browser-based crawler that captures whole sites, including JavaScript-heavy ones, into WACZ archives from a single container.
- [HTTrack](https://www.httrack.com/) - Long-standing website copier that mirrors entire sites for offline browsing.
- [Monolith](https://github.com/Y2Z/monolith) - Bundles a complete web page, assets included, into a single self-contained HTML file.
- [ReplayWeb.page](https://replayweb.page/) - Viewer that opens WARC and WACZ web archives fully offline, in the browser or as a desktop app.
- [SingleFile](https://github.com/gildas-lormeau/SingleFile) - Browser extension that saves any page as one faithful, self-contained HTML file.
- [Zimit](https://github.com/openzim/zimit) - Crawls any website into a ZIM archive readable by Kiwix.

## Preservation, Packaging, and Verification
*Capture makes a copy; preservation keeps it verifiable and readable years later.*

- [Archivematica](https://www.archivematica.org/) - Digital-preservation system by Artefactual that processes collections into standards-based, self-describing archival packages for long-term storage.
- [BagIt](https://datatracker.ietf.org/doc/rfc8493/) - IETF specification (RFC 8493) for packaging files with checksum manifests so a collection can be verified after every copy or transfer; implementations exist for most languages.

## Sneakernets and Offline Transfer
*Knowledge that travels by hand.*

- [apt-offline](https://github.com/rickysarraf/apt-offline) - Updates and installs Debian and Ubuntu packages on machines that never touch the network.
- [NNCP](http://www.nncpgo.org/) - Encrypted store-and-forward file and mail exchange over removable media, sneakernets, and intermittent links.

## Case Studies

- [El Paquete Semanal](https://en.wikipedia.org/wiki/El_Paquete_Semanal) - Cuba's weekly terabyte of media and software, distributed nationwide by hand on hard drives — arguably the world's largest sneakernet.

## Guides and Communities

- [ArchiveTeam](https://wiki.archiveteam.org/) - Volunteer collective racing to save at-risk websites; its wiki documents formats, targets, and rescue tooling.
- [digipres.org](https://www.digipres.org/) - Community-maintained index of digital-preservation tools, formats, and practice.

## Graveyard
*Projects that shaped offline knowledge access but are no longer maintained. Kept for the historical record.*

- [LibraryBox](https://github.com/LibraryBox-Dev/LibraryBox-core) - Portable offline file-sharing and library server, forked from PirateBox for libraries and classrooms. **Discontinued** (repository inactive since 2017).
- [XOWA](https://github.com/gnosygnu/xowa) - Standalone offline Wikipedia reader with its own wiki database engine. **Discontinued** (repository inactive since 2022).

## Other Related Lists

- [awesome-decentralized-web](https://github.com/gdamdam/awesome-decentralized-web) - Peer-to-peer, federated, and local-first software: who controls the infrastructure.
- [awesome-resilient-communication](https://github.com/gdamdam/awesome-resilient-communication) - Communication during shutdowns, disasters, and off-grid operation.
- [awesome-web-archiving](https://github.com/iipc/awesome-web-archiving) - Web archiving in depth, maintained by the IIPC.

## Contributors

Thanks to [all contributors](https://github.com/gdamdam/awesome-offline-knowledge/graphs/contributors). Contributions are welcome — see the contributing guide above.

This work is dedicated to the public domain under [CC0 1.0](LICENSE).
