# Wes Tolbert Recommendations — Catalog Data

This repository holds the live catalog for [wes-tolbert-books.lovable.app](https://wes-tolbert-books.lovable.app) in a single file: **catalog.json**.

The site loads its books, categories, products, and mental models from this file at runtime. Editing the file updates the store — no site rebuild needed.

## catalog.json structure

- `categories` — the store's category tabs (Books, Electronics, Home Goods, Health Products, Services, Finance, Travel)
- `books` — book listings: title, author, genre, themes, cover, description, `amazonUrl` / `audibleUrl` (stored clean; the site adds the Associates tag at render), price, rating, year, curated `list`, and linked `mentalModels`
- `products` — non-book listings. Amazon products use `amazonUrl`; referral/service listings use `externalUrl` + `ctaLabel` with `referral: true`, and may appear in extra categories via `alsoIn`
- `mentalModels` — the Mental Model Warehouse entries books can reference by id
- `listOptions` — the curated shelf labels (Staff picks, New arrivals, Trending now)

Amazon and Audible URLs are always stored without the `?tag=` parameter; the site appends the Associates tag when rendering.
