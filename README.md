# Awesome Offline Knowledge [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of content, tools, and infrastructure for keeping knowledge accessible without the internet — for disasters, shutdowns, remote regions, classrooms, and the long term.

**Scope.** This list is about *offline access to knowledge*: openly licensed content you can store locally, tools to read, serve, and capture it, and the ways it travels without a network. It completes a triangle with two sibling lists, both under *Other Related Lists* below: **awesome-decentralized-web** (who controls the infrastructure) and **awesome-resilient-communication** (how people communicate when infrastructure fails).

**Out of scope:**
- Pirated or unlicensed content — everything listed is openly licensed, public domain, or a tool.
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

- [Content Collections](#content-collections)
- [Readers and Reference Tools](#readers-and-reference-tools)
- [Offline Servers and Learning Platforms](#offline-servers-and-learning-platforms)
- [Maps and Navigation](#maps-and-navigation)
- [Capture and Archiving Tools](#capture-and-archiving-tools)
- [Sneakernets and Offline Transfer](#sneakernets-and-offline-transfer)
- [Case Studies](#case-studies)
- [Guides and Communities](#guides-and-communities)
- [Graveyard](#graveyard)
- [Other Related Lists](#other-related-lists)
- [Contributors](#contributors)

## Content Collections
*The knowledge itself: bulk-downloadable, openly licensed.*

- [Appropedia](https://www.appropedia.org/) - Wiki of appropriate technology, sustainability, and development knowledge, with offline exports available through Kiwix.
- [Hesperian Health Guides](https://hesperian.org/) - Publisher of *Where There Is No Doctor* and other field-medicine guides written for places without professional care, with open digital editions.
- [Kiwix Library](https://library.kiwix.org/) - Catalog of ready-made ZIM archives: all of Wikipedia, Stack Exchange, Project Gutenberg, medical references, and hundreds more.
- [LibriVox](https://librivox.org/) - Public-domain audiobooks read by volunteers, all downloadable for offline listening.
- [Project Gutenberg](https://www.gutenberg.org/) - More than 75,000 public-domain e-books, downloadable in bulk.
- [Software Heritage](https://www.softwareheritage.org/) - Universal archive of software source code, preserving hundreds of millions of projects for the long term.
- [Standard Ebooks](https://standardebooks.org/) - Carefully typeset, open-licensed editions of public-domain e-books.
- [Tatoeba](https://tatoeba.org/) - Openly licensed database of millions of example sentences and their translations across hundreds of languages, downloadable in full.
- [Wikimedia Dumps](https://dumps.wikimedia.org/) - Complete database exports of Wikipedia and its sister projects, the raw material behind most offline encyclopedia tools.

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
- [RACHEL](https://worldpossible.org/) - Preloaded offline education server used in schools and community centers without connectivity, by World Possible.

## Maps and Navigation

- [CoMaps](https://www.comaps.app/) - Community-governed offline maps and navigation app built on OpenStreetMap data, forked from Organic Maps.
- [OpenStreetMap](https://www.openstreetmap.org/) - The openly licensed map of the world; its data extracts power every offline maps app on this list.
- [Organic Maps](https://organicmaps.app/) - Offline maps and navigation app built on OpenStreetMap data, with detailed hiking and cycling coverage.
- [OsmAnd](https://osmand.net/) - Highly configurable offline maps, navigation, and map-editing app built on OpenStreetMap data.
- [Protomaps](https://protomaps.com/) - Serves an entire planet of map tiles from one static file (PMTiles), making self-hosted offline maps practical.

## Capture and Archiving Tools
*Make your own offline copies while the network is still up.*

- [ArchiveBox](https://archivebox.io/) - Self-hosted web archive that snapshots the pages you feed it into several durable formats.
- [HTTrack](https://www.httrack.com/) - Long-standing website copier that mirrors entire sites for offline browsing.
- [Monolith](https://github.com/Y2Z/monolith) - Bundles a complete web page, assets included, into a single self-contained HTML file.
- [SingleFile](https://github.com/gildas-lormeau/SingleFile) - Browser extension that saves any page as one faithful, self-contained HTML file.
- [Zimit](https://github.com/openzim/zimit) - Crawls any website into a ZIM archive readable by Kiwix.

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
