# MaDTracker

> Play Smarter Not Harder. MaDTiA.

MaDTracker is a privacy-first torrent tracker and indexer that runs entirely over HTTPS, replacing the traditional UDP tracker model with a faster, more secure, and more private alternative. Torrents are enriched with movie and TV metadata, served through a clean responsive interface, and replicated across multiple mirror domains.

---

## Live Instances

| Domain | Role |
|--------|------|
| https://tracker.madtia.cc | Primary |
| https://edge-team.cc | Mirror |
| https://torrentonline.cc | Mirror |

---

## Features

### Torrent Index
Browse the full torrent library in a responsive card grid. Each card shows poster art, title, release year, a short description, and live seeder/leecher/completed stats updated in real time. A persistent search bar lets you filter across all pages without losing your query.

### Movie and TV Metadata
Torrents are automatically enriched with data from The Movie Database (TMDB), including poster images, titles, release years, and plot overviews. Manual ID input is also supported for precise matching.

### Upload
A drag-and-drop uploader that accepts .torrent files individually or in bulk. Metadata is detected automatically from the filename. Duplicate torrents are recognized and handled gracefully, returning the existing entry instead of creating a copy.

### Torrent Detail
Every torrent has a dedicated page with its full metadata panel, complete file list with sizes, live tracker stats with a manual refresh option, and direct download or magnet link buttons. Rich link previews are supported on Discord, Telegram, WhatsApp, and Facebook.

### Download
A smooth, mirror-aware download flow. Regardless of which domain you access, the file is always served correctly. Mirrors resolve transparently to the primary storage.

### Tracker Status
A live dashboard that checks 100+ public trackers in real time and displays their status, ping, and uptime history. MaDTiA domains are always listed first. The full working tracker list can be copied or downloaded in one click for use in any torrent client.

### Contact
A built-in contact page for support and inquiries.

---

## Tracker Announce URLs

Add these to your torrent client or .torrent files:

```
https://tracker.madtia.cc/announce
https://edge-team.cc/announce
https://torrentonline.cc/announce
udp://node01.trackerstatus.live:42069/announce
udp://node01.madtia.cc:42069/announce
udp://node02.torrentonline.cc:42069/announce
udp://node01.torrentonline.cc:42069/announce
udp://node02.madtia.cc:42069/announce

```

> Only indexed torrents are tracked. Upload your .torrent file first. ( not needed for udp nodes )

---

## Why MaDTracker?

Most public trackers rely on unencrypted UDP, fast but completely exposed. MaDTracker runs entirely over HTTPS, meaning your announces are encrypted end-to-end, resistant to interception, and protected from network-level interference.

Every torrent in the index is enriched with real movie and TV metadata, not just a raw filename. You get posters, descriptions, and release info automatically, making it far easier to find and identify what you are looking for.

The platform is replicated across multiple independent mirror domains, so there is no single point of failure. Downloads always resolve to the correct source transparently, no matter which mirror you hit.

No accounts. No logs. No ads. Just a clean, fast, private tracker that works.

---

## Changelog

### 2025-2026 - Major Architecture Overhaul
A full rebuild of the platform under the hood. Every major component was redesigned or rewritten.

- **TMDB integration** - Torrents are automatically matched against The Movie Database on upload. Poster art, title, release year, and plot overview are fetched and stored per torrent. Manual TMDB ID input also supported, with automatic movie/TV type detection and year-based fallback search
- **Batch AJAX uploader** - Files now upload in batches of up to 15 files / 99 MB, with a real-time progress bar, per-batch error reporting, and collapsible success/error panels
- **Turbo Cache mode** - New config option that switches the tracker to metadata-only mode: the .torrent file is removed after DB insertion, reducing storage footprint
- **Multi-domain mirror architecture** - Downloads are fully domain-aware. Mirror domains proxy file requests transparently to the primary server, no extra file storage required
- **Download flow redesign** - Completely rebuilt with a 4-stage flow: countdown loader, math challenge, download button, animated retrieval sequence with mirror-specific messaging
- **Tracker Status Dashboard** - Live tracker checker via Server-Sent Events (SSE). Checks 100+ public trackers in real time with uptime history, ping averages, and days monitored. Rate limited and cached. MaDTiA domains always pinned first
- **Live stats on cards and detail pages** - Seeders, leechers, peers, and completed counts load asynchronously everywhere, with a manual refresh button and 10 second cooldown
- **Quick preview modal** - Torrent details, file list, magnet, and download accessible via AJAX modal without leaving the index page
- **Human verification gate** - Dedicated verification page protecting the announce endpoint from direct browser access, with a custom checkbox and session token
- **Admin orphan scanner** - Batch tool that detects DB records whose .torrent files are missing on disk, with CSRF protection and progress reporting
- **Admin ACP search** - Secured admin search with session fingerprint binding, periodic session regeneration, and per-user rate limiting
- **File type icon engine** - Auto-detects and displays file-type icons for video, audio, archive, ebook, software, and PDF when no TMDB poster is available
- **Single and multi-file torrent display fixed** - Bencode digit parsing error resolved, both torrent structures handled correctly
- **Comments and webseeds preserved** - Original torrent comments and webseed entries kept intact during re-encoding on upload

---

### Madhex Patch (late 2024)
- Completely recoded peer list structure, faster and more responsive
- Single-file and multi-file torrent display fixed
- Bencode digit parsing error fixed
- Comments and webseeds now preserved after upload
- New security measures added

### 24 Jan 2025
- API structure introduced
- Cross-site remote fetcher in beta testing
- Windows x64 upload tool in progress

### 23 Jan 2025
- Show File List button added to torrent detail pages
- Dynamic page title generation fixed
- Open Graph link previews added for Facebook, WhatsApp, Instagram, Discord, and Telegram

### 22 Jan 2025 - New GUI Release
- Brand new interface launched
- Search bar now retains terms across paginated results
- All ads and popups completely removed
- Contact form added
- Mobile responsive layout updated
- Thank you to everyone who supported, trusted, and used MaDTracker

### 12 Sep 2024
- WebSeed support added, HTTP seeding now available on stored torrents

### 12 Jul 2024
- Upload function fix released
- New function: returns download link if torrent already exists, preventing duplicates
- New function: returns uploaded file URL on successful upload

### 10 Jul 2024
- Code optimized and overall size reduced to around 50 KB

### 08-09 Jul 2024
- Layout improved across all pages
- Download function updated
- Anti-duplicate torrent system introduced
- Mobile layout improved
- Major code updates and optimizations
- Mirror distribution updated
- Minor fixes pushed to all mirrors

---

## Donate

Your support keeps the servers running and the project moving forward. Thank you!

| Method | Address |
|--------|---------|
| Bitcoin (BTC) | `124xkKP7XZFmd44dbWKfKfpahiBcVZFUoV` |
| Ethereum / USDC (ERC-20) | `0x926c537dc3396dbde0a836ab4cb9be0a00ac3467` |
| Ko-fi | https://ko-fi.com/madtia |

---

## Privacy

- No content tracking
- No IP addresses or cookies logged
- No personal data stored, only torrent metadata
