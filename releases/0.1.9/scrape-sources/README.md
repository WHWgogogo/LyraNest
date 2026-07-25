# Scraper source JSON

Open **Scrape** in LyraNest and select **Import JSON**. The server hot-loads the configuration immediately.

`lyranest-direct-sources.json` is a standalone import file for NetEase, QQ Music, and KuGou. It is intentionally distributed only in this release folder and is not embedded in the server or clients.

The loader accepts version-1 documents. Search mappings require `items_path`, `id_field`, and `title_field`; optional mappings include artist, album, album artist, year, track number, disc number, genre, cover, and lyrics.