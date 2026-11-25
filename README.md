# Explore the Pushto Dictionary in Python

A real, runnable notebook for [pushtodictionary.com](https://pushtodictionary.com) — a free trilingual Pashto dictionary with 126,000+ entries, Kandahari & Peshawari pronunciations, and English & Urdu meanings.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Aziz0346/pushto-dictionary-notebooks/blob/main/pushto-dictionary-explore-pashto-words.ipynb)

## What is in this repo

| File | What it is |
|---|---|
| `pushto-dictionary-explore-pashto-words.ipynb` | The notebook. Run it in Colab — no setup, no keys. |
| `pushto-dictionary-1000-words.csv` | The sample: 1,000 Pashto words with English gloss + live word-page link. |
| `pushto-dictionary-1000-words.json` | Same sample as JSON. |
| `LICENSE` | CC BY 4.0 — the sample is free to use with credit to pushtodictionary.com. |

## What the notebook does

1. **Loads the 1,000-word sample** (local file, or the raw GitHub URL as fallback).
2. **Charts it** — words by first letter (44 Pashto letters), word-length distribution, part of speech for the subset that has one.
3. **Searches it** — type `kitab` or `کتاب` or `book` and get the entry with its live word page. Romanized search is diacritic-insensitive, so `kitab` finds the API's `kitā́b`.
4. **Proves a real Pashto pitfall live** — the two Yehs. Pashto uses Farsi Yeh `ی` (U+06CC); Arabic Yeh `ي` (U+064A) looks identical but is a different character. The notebook checks both spellings against the live site (both redirect 308 to the Farsi spelling, verified 25 Nov 2026) and shows the one-line normalisation that fixes it.

## Where the sample came from

- 977 words from the dictionary's own [Top 1000 Pashto Words](https://pushtodictionary.com/learn/top-1000-pashto-words) page (English gloss + live link as published there).
- 6 phrase pages (`/learn/...`) linked from that page, each verified live (HTTP 200).
- 17 entries verified live through the site's own search API (`/api/v1/search`), exact match, verified entries only.
- Romanization, Urdu gloss and part of speech were filled in wherever the site's search API returned an exact verified match; the loader cell prints the exact counts. Nothing in the sample is invented — a row without a romanization simply has an empty field.

Built 25 November 2026. Every row links to its live word page on pushtodictionary.com.

## The indexing test (why this repo exists)

This is a **single honest test** of whether a genuine, useful notebook gets indexed — not an article stuffed into a notebook. The test protocol:

- **Day 0** (fill in when published): notebook live. Record the GitHub URL + the Colab URL + date below.
- **Day 1, 3, 7, 14:** Google `site:colab.research.google.com/github/Aziz0346` and the exact notebook title in quotes. Indexed? Ranking for what? Also check Bing.
- **Kill rule:** if it is not indexed by Day 14, stop. Do not publish 10 more notebooks to "force" it. One test, one result, one decision.
- **Keep rule:** if it *is* indexed and gets any traffic, GitHub stars or forks, make **one notebook per month**, each a real tool (transliteration converter, proverb explorer, verb-conjugation explorer) — never an article.

### Day 0 record

- GitHub URL: https://github.com/Aziz0346/pushto-dictionary-notebooks
- Colab URL: https://colab.research.google.com/github/Aziz0346/pushto-dictionary-notebooks/blob/main/pushto-dictionary-explore-pashto-words.ipynb
- Published: 25 November 2026

## Learn more

- The dictionary: [pushtodictionary.com](https://pushtodictionary.com)
- Learn Pashto: [pushtodictionary.com/learn](https://pushtodictionary.com/learn)
- Proverbs: [pushtodictionary.com/mataloona](https://pushtodictionary.com/mataloona)
- Word of the Day: [pushtodictionary.com/word-of-the-day](https://pushtodictionary.com/word-of-the-day)
- Live search API (no key needed): `https://pushtodictionary.com/api/v1/search?q=کتاب`
