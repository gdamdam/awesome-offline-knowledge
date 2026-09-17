# Awesome Offline Knowledge [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of content, tools, and infrastructure for keeping knowledge accessible without the internet: for disasters, shutdowns, remote regions, and the long term.

**Scope.** Content licensed for offline storage and redistribution, tools to read, serve, and capture it, and the ways it travels without a network.

It completes a triangle with two sibling lists, both under *Other Related Lists* below:

- [awesome-decentralized-web](https://github.com/gdamdam/awesome-decentralized-web#readme): who controls the infrastructure.
- [awesome-resilient-communication](https://github.com/gdamdam/awesome-resilient-communication#readme): how people communicate when infrastructure fails.

**Out of scope:**
- Pirated or unlicensed content. Everything here is public domain, openly licensed, or free to download and redistribute offline for noncommercial use. Entries with restrictions say so.
- Cryptocurrency- and token-dependent projects.
- AI tools and agent frameworks.
- General self-hosting software without an offline-first purpose.

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a project.

**How to read this list.** "Offline knowledge" means three different things, and you usually need all three:

- **Content**: the knowledge itself, in bulk, licensed for offline use. *(Wikimedia dumps, Project Gutenberg, OpenStreetMap)*
- **Tools**: readers, servers, and capture software that make content usable off the network. *(Kiwix, Calibre, ArchiveBox)*
- **Transport**: how content moves without connectivity: hotspots, removable media, sneakernets. *(Internet-in-a-Box, NNCP)*

**Dormant** entries still work but their repository has had no activity for over 2 years; the tag gives the date. Dead projects are in the Graveyard at the bottom.

**How this list is maintained.** Inclusion, exclusion, and the criteria above are decided by a human maintainer, me, by hand. AI tooling helps draft entry text and cross-check licenses, sizes, and project status. Every claim is verified against the project's own documentation before it lands.

## Contents

- [Prepare Before You Need It](#prepare-before-you-need-it)
- [Choose by Scenario](#choose-by-scenario)
- [Deployment at a Glance](#deployment-at-a-glance)
- [Knowledge per Gigabyte](#knowledge-per-gigabyte)
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
Everything on this list works only if it was downloaded, installed, and tested while the network still worked. Preparation takes an afternoon and the checklist is short:

- Download content and the apps that read it in advance. Check free storage before starting a multi-gigabyte archive.
- Test the full setup with Wi-Fi and cellular off: first launch, opening content, search. Nothing should need an online login, license activation, DNS lookup, or cloud API.
- Keep at least two verified copies on different storage devices.
- Verify checksums or signatures where the source publishes them.
- Record each archive's version and date, and set a refresh schedule. Maps, medical references, and software documentation all age at different rates.
- Store readers and installers alongside the content. An archive is useless without compatible software for your platform.
- Keep short startup instructions on the same media, printed or as plain text, so someone else can bring the system up.
- Plan for power: charged devices, power banks, solar charging for long outages, and a low-power server such as a Raspberry Pi where a hub must stay running.
- If you run a community server, test it from several client devices over its own Wi-Fi, not only from the machine it runs on.
- Prefer formats that stay usable without a specific vendor or account. Plain files outlive app-locked libraries.
- For medical and emergency material, note the edition date. Offline references age, and none replace qualified professional help.

## Choose by Scenario
Reasonable starting combinations, drawn from the entries below. Starting points, not guarantees. The medical caveat above applies throughout.

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
The collections most often deployed in bulk, compared on what matters when you buy hardware. Sizes are from September 2026 and only grow. Treat them as planning numbers and check before buying media.

|System                               |Size                                                           |Updates                                                |Licenses                               |Runs on                       |
|-------------------------------------|---------------------------------------------------------------|-------------------------------------------------------|---------------------------------------|------------------------------|
|Kiwix (ZIM archives)                 |MBs per archive, up to 119 GB for English Wikipedia with images|✗ re-download the whole ZIM                            |Reader GPLv3, content mostly CC BY-SA  |Desktop, mobile, Raspberry Pi |
|Wikimedia dumps (XML/SQL)            |About 20 GB compressed for English Wikipedia text              |✗ new full dumps about twice a month                   |CC BY-SA / GFDL                        |Raw data, any tool            |
|Project Gutenberg (EPUB, HTML, text) |MBs per book, about 1 TB for a full mirror                     |✓ rsync sends only what changed                        |Public domain (US)                     |Any e-book reader             |
|OpenStreetMap data (PBF)             |88 GB planet file, country extracts far smaller                |✓ replication diffs, minutely to daily                 |ODbL                                   |Raw data, any tool            |
|Organic Maps / CoMaps / OsmAnd       |Hundreds of MB per country                                     |◐ OsmAnd has live diffs, the others re-download regions|Apps open source, map data ODbL        |Android, iOS                  |
|Kolibri (content channels)           |GBs, depends on the channels                                   |✓ device-to-device sync built in                       |Platform MIT, content varies by channel|Desktop, Android, Raspberry Pi|
|Internet-in-a-Box (ZIM, Kolibri, OSM)|64 GB card to 1 TB+ drive                                      |✗ admin console re-downloads packages                  |Open stack, content varies             |Raspberry Pi, Linux           |
|RACHEL (module bundles)              |Hundreds of GB, sized to the device                            |✗ module downloads or USB from World Possible          |Mixed open licenses per module         |RACHEL devices, Raspberry Pi  |

✓ incremental updates · ◐ partial · ✗ updating means re-downloading the whole archive

What this means in practice: on slow or metered links, prefer the systems with incremental updates (rsync, OSM diffs, Kolibri sync) and refresh ZIM files by sneakernet now and then. And check content licenses separately from software licenses. Handing someone a preloaded device redistributes everything on it.

Sources: the [Kiwix download server](https://download.kiwix.org/zim/wikipedia/) (119 GB for the 2026-08 English Wikipedia with images), [Planet OSM](https://planet.openstreetmap.org/) (88 GB PBF, 2026-09), and Project Gutenberg's [mirroring how-to](https://www.gutenberg.org/help/mirroring.html). The dump and full-mirror totals are estimates.

## Knowledge per Gigabyte
What fits on a given card or stick, using the file sizes Kiwix published in September 2026. Kiwix offers most large collections in three editions: *maxi* (text and images), *nopic* (text only), and *mini* (article introductions only). The text-only and mini editions hold most of the knowledge at a fraction of the size. That is what makes small budgets work. Figures are rounded, grow between builds, and leave no room for the reader software itself.

|Storage                   |What fits                                                                                                                           |Sizes                                                                                                 |
|--------------------------|------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
|1 GB (spare phone storage)|WikiMed without images fills it. Or WikiMed mini plus Appropedia and PhET.                                                          |WikiMed nopic 822 MB · WikiMed mini 155 MB · Appropedia 555 MB · PhET 104 MB                          |
|4 GB (small USB stick)    |Simple English Wikipedia with images, WikiMed mini, and a country map. Or iFixit alone.                                             |Simple English Wikipedia maxi 3.2 GB · WikiMed mini 155 MB · Kenya OSM 0.4 GB · iFixit 3.3 GB         |
|16 GB (microSD card)      |English Wikipedia mini (the introduction of every article), WikiMed with images, Appropedia, and PhET.                              |Wikipedia mini 12 GB · WikiMed maxi 2.1 GB · Appropedia 555 MB · PhET 104 MB                          |
|64 GB                     |English Wikipedia without images, Wiktionary, and WikiMed with images. Nearly full. iFixit or a country map need a 128 GB card.     |Wikipedia nopic 49 GB · Wiktionary nopic 8.5 GB · WikiMed maxi 2.1 GB                                 |
|128 GB                    |Full English Wikipedia with images, plus iFixit and PhET in the space left.                                                         |Wikipedia maxi 119 GB · iFixit 3.3 GB · PhET 104 MB                                                   |
|256 GB                    |Full English Wikipedia with images and all of Stack Overflow, plus Wiktionary, iFixit, WikiMed, and a large country map.            |Wikipedia maxi 119 GB · Stack Overflow 107 GB · Wiktionary 8.5 GB · iFixit 3.3 GB · Germany OSM 4.8 GB|
|1 TB and up               |All of the above, the Project Gutenberg ZIM, and a continent of maps or the whole OSM planet. Internet-in-a-Box or RACHEL territory.|Gutenberg 206 GB · United States OSM 12 GB · OSM planet 88 GB                                         |

Three things the numbers say. Images are expensive: English Wikipedia goes from 49 GB to 119 GB with them, so text-only editions win when storage is tight. A medical reference is the cheapest high-value item here: WikiMed's full text is under 1 GB. And collections jump rather than grow: the Gutenberg ZIM went from 72 GB in 2023-08 to 206 GB in 2025-11, so re-check sizes before refreshing media bought for an older build.

Sources: the ZIM sizes are the file sizes listed on the [Kiwix download server](https://download.kiwix.org/zim/) for the newest build of each title as of 2026-09. Map sizes are Geofabrik's current `-latest.osm.pbf` extracts and the Planet OSM file, both linked in the table above.

|Collection              |Edition|ZIM file                              |Size  |
|------------------------|-------|--------------------------------------|------|
|English Wikipedia       |maxi   |`wikipedia_en_all_maxi_2026-08`       |119 GB|
|English Wikipedia       |nopic  |`wikipedia_en_all_nopic_2026-06`      |49 GB |
|English Wikipedia       |mini   |`wikipedia_en_all_mini_2026-06`       |12 GB |
|Simple English Wikipedia|maxi   |`wikipedia_en_simple_all_maxi_2026-05`|3.2 GB|
|WikiMed                 |maxi   |`wikipedia_en_medicine_maxi_2026-04`  |2.1 GB|
|WikiMed                 |nopic  |`wikipedia_en_medicine_nopic_2026-04` |822 MB|
|WikiMed                 |mini   |`wikipedia_en_medicine_mini_2026-04`  |155 MB|
|Wiktionary              |nopic  |`wiktionary_en_all_nopic_2026-08`     |8.5 GB|
|Stack Overflow          |all    |`stackoverflow.com_en_all_2026-07`    |107 GB|
|Project Gutenberg       |all    |`gutenberg_en_all_2025-11`            |206 GB|
|iFixit                  |all    |`ifixit_en_all_2025-12`               |3.3 GB|
|Appropedia              |maxi   |`appropedia_en_all_maxi_2026-02`      |555 MB|
|PhET                    |all    |`phet_en_all_2026-08`                 |104 MB|

## Content Collections
*The knowledge itself, in bulk. The license is stated wherever it is not fully open.*

### General Reference
- [Kiwix Library](https://library.kiwix.org/) - Catalog of ready-made ZIM archives: all of Wikipedia, Stack Exchange, Project Gutenberg, medical references, and hundreds more.
- [Wikimedia Dumps](https://dumps.wikimedia.org/) - Complete database exports of Wikipedia and its sister projects (CC BY-SA). The raw material behind most offline encyclopedia tools.

### Health and Medicine
*Offline medical references age. Record the edition date, and treat them as support for qualified professional care, never a replacement.*

- [Hesperian Health Guides](https://hesperian.org/) - Publisher of *Where There Is No Doctor* and other field-medicine guides written for places without professional care. Digital editions are free to download under a custom open-copyright policy. Its restrictions vary by edition and can require permission for commercial use, digital or large-scale redistribution, and translation.
- [WikiMed](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Medicine/App) - Offline snapshot of Wikipedia's medical articles (CC BY-SA), maintained with WikiProject Medicine. Distributed as a Kiwix ZIM and a mobile app.

### Education and Learning
- [OpenStax](https://openstax.org/) - Peer-reviewed college textbooks, free to download as PDF. Licenses vary by title between CC BY and CC BY-NC-SA. The noncommercial titles are not fully open.
- [PhET Interactive Simulations](https://phet.colorado.edu/) - Math and science simulations from the University of Colorado Boulder, downloadable one by one or as a complete offline website installer. The published simulations are CC BY-NC 4.0, a noncommercial restriction. Their source code is open source.

### Books and Languages
- [LibriVox](https://librivox.org/) - Public-domain audiobooks read by volunteers. All downloadable for offline listening.
- [Project Gutenberg](https://www.gutenberg.org/) - More than 75,000 public-domain e-books, downloadable in bulk.
- [Standard Ebooks](https://standardebooks.org/) - Carefully typeset, open-licensed editions of public-domain e-books.
- [Tatoeba](https://tatoeba.org/) - Openly licensed database of millions of example sentences and their translations in hundreds of languages. Downloadable in full.

### Technical and Practical Knowledge
- [Appropedia](https://www.appropedia.org/) - Wiki of appropriate technology, sustainability, and development knowledge. Offline exports available through Kiwix.
- [iFixit](https://www.ifixit.com/) - Repair manuals for phones, computers, appliances, and vehicles, written by a large community. The guides are CC BY-NC-SA 3.0, a noncommercial restriction. Available in full as a Kiwix ZIM.
- [Software Heritage](https://www.softwareheritage.org/) - Universal archive of software source code. Preserves hundreds of millions of projects for the long term.

## Readers and Reference Tools
*Software for using stored knowledge on your own device.*

- [Aard2](https://aarddict.org/) - Android dictionary and Wikipedia reader for slob-format offline archives.
- [Calibre](https://calibre-ebook.com/) - The standard tool for e-book library management, format conversion, and reading.
- [DevDocs](https://devdocs.io/) - Combined API documentation browser for hundreds of programming tools. Can be installed for fully offline use.
- [GoldenDict-ng](https://github.com/xiaoyifang/goldendict-ng) - Dictionary application that reads StarDict, Babylon, and many other offline dictionary formats.
- [Kiwix](https://kiwix.org/) - Reader and server for ZIM archives on desktop, mobile, and Raspberry Pi. The standard way to use Wikipedia offline.
- [KOReader](https://koreader.rocks/) - Document and e-book reader for e-ink devices, phones, and desktops.
- [Zeal](https://zealdocs.org/) - Offline documentation browser for developers, using Dash-format docsets.

## Offline Servers and Learning Platforms
*A box that serves knowledge to everyone nearby.*

- [Internet-in-a-Box](https://iiab.io/) - Turns a Raspberry Pi into a local knowledge hotspot serving Wikipedia, maps, books, and lessons to nearby devices.
- [Kolibri](https://learningequality.org/kolibri/) - Offline-first learning platform that syncs curricula between devices without internet. By Learning Equality.
- [MoodleBox](https://moodlebox.net/) - Self-contained Moodle server on a Raspberry Pi that broadcasts its own Wi-Fi network. For courses and quizzes in classrooms without connectivity.
- [RACHEL](https://worldpossible.org/) - Preloaded offline education server used in schools and community centers without connectivity. By World Possible.

## Maps and Navigation

- [CoMaps](https://www.comaps.app/) - Community-governed offline maps and navigation app built on OpenStreetMap data. Forked from Organic Maps.
- [Geofabrik Downloads](https://download.geofabrik.de/) - Daily updated OpenStreetMap extracts (ODbL) by continent, country, and region. The practical way to get map data at a downloadable size.
- [OpenStreetMap](https://www.openstreetmap.org/) - The openly licensed map of the world. Its data extracts power every offline maps app on this list.
- [Organic Maps](https://organicmaps.app/) - Offline maps and navigation app built on OpenStreetMap data, with detailed hiking and cycling coverage.
- [OsmAnd](https://osmand.net/) - Highly configurable offline maps, navigation, and map-editing app built on OpenStreetMap data.
- [Protomaps](https://protomaps.com/) - Serves a whole planet of map tiles from one static file (PMTiles). Makes self-hosted offline maps practical.

## Capture and Web Archiving
*Make your own offline copies while the network is still up.*

- [ArchiveBox](https://archivebox.io/) - Self-hosted web archive that snapshots the pages you feed it into several durable formats.
- [ArchiveWeb.page](https://archiveweb.page/) - Browser extension and desktop app by Webrecorder that records the pages you browse into portable WACZ archives, entirely on your own machine.
- [Browsertrix Crawler](https://github.com/webrecorder/browsertrix-crawler) - Browser-based crawler that captures whole sites, including JavaScript-heavy ones, into WACZ archives from a single container.
- [HTTrack](https://www.httrack.com/) - Long-running website copier that mirrors entire sites for offline browsing.
- [Monolith](https://github.com/Y2Z/monolith) - Bundles a complete web page, assets included, into a single self-contained HTML file.
- [ReplayWeb.page](https://replayweb.page/) - Viewer that opens WARC and WACZ web archives fully offline, in the browser or as a desktop app.
- [SingleFile](https://github.com/gildas-lormeau/SingleFile) - Browser extension that saves any page as one faithful, self-contained HTML file.
- [Zimit](https://github.com/openzim/zimit) - Crawls any website into a ZIM archive readable by Kiwix.

## Preservation, Packaging, and Verification
*Capture makes a copy. Preservation keeps it verifiable and readable years later.*

- [Archivematica](https://www.archivematica.org/) - Digital-preservation system by Artefactual that processes collections into standards-based, self-describing archival packages for long-term storage.
- [BagIt](https://datatracker.ietf.org/doc/rfc8493/) - File-packaging format with checksum manifests, so a collection can be verified after every copy or transfer. Defined in RFC 8493, an informational Independent Submission. Implementations exist for most languages.

## Sneakernets and Offline Transfer
*Knowledge that travels by hand.*

- [apt-offline](https://github.com/rickysarraf/apt-offline) - Updates and installs Debian and Ubuntu packages on machines that never touch the network.
- [NNCP](http://www.nncpgo.org/) - Encrypted store-and-forward file and mail exchange over removable media, sneakernets, and intermittent links.

## Case Studies

- [El Paquete Semanal](https://en.wikipedia.org/wiki/El_Paquete_Semanal) - Cuba's weekly terabyte of media and software, distributed nationwide by hand on hard drives. Arguably the largest sneakernet in the world.

## Guides and Communities

- [ArchiveTeam](https://wiki.archiveteam.org/) - Volunteer collective racing to save at-risk websites. Its wiki documents formats, targets, and rescue tooling.
- [digipres.org](https://www.digipres.org/) - Community-maintained index of digital-preservation tools, formats, and practice.

## Graveyard
*Projects that shaped offline knowledge access and are no longer maintained. Kept for the record.*

- [LibraryBox](https://github.com/LibraryBox-Dev/LibraryBox-core) - Portable offline file-sharing and library server, forked from PirateBox for libraries and classrooms. **Discontinued** (repository inactive since 2017).
- [XOWA](https://github.com/gnosygnu/xowa) - Standalone offline Wikipedia reader with its own wiki database engine. **Discontinued** (repository inactive since 2022).

## Other Related Lists

- [awesome-decentralized-web](https://github.com/gdamdam/awesome-decentralized-web) - Peer-to-peer, federated, and local-first software: who controls the infrastructure.
- [awesome-resilient-communication](https://github.com/gdamdam/awesome-resilient-communication) - Communication during shutdowns, disasters, and off-grid operation.
- [awesome-web-archiving](https://github.com/iipc/awesome-web-archiving) - Web archiving in depth, maintained by the IIPC.

## Contributors

Thanks to [all contributors](https://github.com/gdamdam/awesome-offline-knowledge/graphs/contributors). Contributions are welcome. See the contributing guide above.

This work is dedicated to the public domain under [CC0 1.0](LICENSE).
