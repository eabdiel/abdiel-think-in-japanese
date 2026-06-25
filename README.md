# Think in Japanese Portal

A fully offline-capable Japanese learning portal built as a static HTML/CSS/JavaScript website.

The portal combines kana practice, kanji study, phrase-based thinking practice, reading aids, frequency-based character review, and a structured 90-day study path. It is designed for learners who want to start thinking in Japanese through short, practical phrases instead of only studying grammar rules in isolation.

Live site:

https://thinkinjapanese.com

Created by Edwin A. Rodriguez / ProgreTech.

---

## What This Project Includes

Think in Japanese is a bilingual English/Spanish learning site with no backend and no account system. It can be hosted online or downloaded and used locally.

Main tools included:

- Home study hub
- Kana Dojo practice game
- Kanji Hub
- 90-Day Study Tracker
- Phrase Set 1: foundational internal-monologue phrases
- Phrase Set 2: casual daily-use phrases
- Phrase Set 3: Gaki/Kansai-style reaction phrases
- Reading Aid for characters appearing in the phrase sets
- Frequency Deck for high-value character recognition
- 90-Day Study Plan
- English and Spanish versions of the learning pages
- Theme selector with Pixel Pastel, Cream Garden, and Tokyo Night themes

---

## Offline Friendly

One of the primary goals of this project is that the entire site works without a server, database, login, API key, or internet connection.

After downloading the repository, you can open `index.html` directly in a browser and study locally.

This makes the portal useful for:

- Airplane travel
- Commutes
- Tablets without internet access
- School or work breaks
- Portable study folders or USB drives
- Long-term personal archives

The site uses local HTML, CSS, JavaScript, and asset files. Browser features such as `localStorage` are used where possible for local settings and progress tracking.

---

## Online Version

The hosted version is available at:

https://thinkinjapanese.com

The online version is the same style of static site, but hosted for easier access across devices.

---

## Installation

### Option 1: Download and Open Locally

Download or clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/think-in-japanese-portal.git
```

Then open:

```text
index.html
```

in your browser.

No installation step is required.

### Option 2: Host on Any Static Web Host

Because the site is static, it can be hosted on:

- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages
- A normal web hosting account
- Any server capable of serving HTML/CSS/JS files

Upload the files and make sure `index.html` is at the web root.

---

## Suggested Folder Structure

A typical deployed copy should look like this:

```text
public_html/
  index.html
  index_es.html
  kana_dojo.html
  kana_dojo_es.html
  kanji_hub.html
  kanji_hub_es.html
  japanese_90_day_calendar_tracker.html
  japanese_90_day_calendar_tracker_es.html
  think_in_japanese_100_phrases_part1_reformatted.html
  think_in_japanese_100_phrases_part1_reformatted_es.html
  think_in_japanese_100_casual_phrases_part2.html
  think_in_japanese_100_casual_phrases_part2_es.html
  think_in_japanese_100_gaki_style_phrases_part3.html
  think_in_japanese_100_gaki_style_phrases_part3_es.html
  think_in_japanese_character_reading_aid_part4.html
  think_in_japanese_character_reading_aid_part4_es.html
  think_in_japanese_part5_frequency_deck.html
  think_in_japanese_part5_frequency_deck_es.html
  think_in_japanese_part6_90_day_plan.html
  think_in_japanese_part6_90_day_plan_es.html
  pixel-theme-v2.css
  sitemap.xml
  assets/
```

File names may change over time, but the pages above represent the core site layout.

---

## Core Learning Philosophy

The project is built around a simple progression:

1. Learn useful Japanese thoughts first.
2. Practice those thoughts out loud.
3. Learn the kana and kanji that appear inside those thoughts.
4. Reduce romaji dependency over time.
5. Use the 90-day tracker and study plan to stay consistent.

The goal is not to memorize every phrase perfectly in one pass. The goal is to create repeated contact with practical Japanese until phrases, kana, and kanji begin connecting directly to meaning.

---

## Page-by-Page Overview

### `index.html` and `index_es.html`

The main hub pages introduce the learning path and link to each study tool.

They explain how to use the portal as a learning map:

- Phrase Sets 1–3 for Japanese thought patterns
- Reading Aid and Frequency Deck for character recognition
- Kana Dojo and Kanji Hub for practice
- 90-Day Tracker and Study Plan for structure
- Gradual romaji reduction

### `kana_dojo.html` and `kana_dojo_es.html`

Kana Dojo is an interactive kana recognition game.

Core behavior:

- Shows a romaji prompt.
- User clicks kana tiles in order.
- Tracks correct and incorrect attempts.
- Supports hiragana and katakana practice.
- Includes dakuten/handakuten support.
- Includes optional hiding or showing of row labels and mnemonic labels.
- Maintains game history during the session.
- Supports a downloadable session report.
- Can be extended with an external JSON word list.

Important internal concepts:

- Kana tiles are generated from predefined kana groups.
- The active word is selected from a local word bank.
- The user answer is built by appending clicked kana.
- A validation function compares the selected kana sequence against the expected kana string.
- Session history records romaji, kana, translation, and result.

### `kanji_hub.html` and `kanji_hub_es.html`

Kanji Hub is a standalone kanji study page inspired by the structure of Kana Dojo, but optimized for kanji recognition.

Core behavior:

- Displays kanji cards in manageable batches.
- Starts with kanji from the Part 4 Reading Aid.
- Expands into common Japanese kanji cards.
- Supports batch selection such as core, top 50, top 100, and prepared larger views.
- Allows grouping by reading family, source, or no grouping.
- Includes search by kanji, romaji, meaning, or example.
- Includes a shuffle function for visible cards.
- Includes an example bank for reading practice.

Each card includes:

- Kanji character
- Reading / romaji
- Meaning or anchor phrase
- Mnemonic guidance
- Japanese example
- Romaji example
- Natural translation
- Source/tier information

Important internal concepts:

- `KANJI_DATA` contains the kanji card records.
- `EXAMPLE_BANK` contains word or sentence examples.
- The current batch filter controls which cards are visible.
- The grouping dropdown reorganizes the visible cards by reading family or source.
- The search input filters the current working set.
- The shuffle button randomizes the currently visible cards without changing the underlying data.

### Phrase Pages: Parts 1–3

The phrase pages contain the core Think in Japanese material.

- Part 1 focuses on foundational internal monologue.
- Part 2 focuses on casual natural phrasing.
- Part 3 focuses on Gaki/Kansai-style reactions and humor.

Each phrase entry generally includes:

- Japanese phrase
- Romaji
- Natural meaning
- Literal brain translation
- Category or usage badge

These pages are meant to be practiced actively, not only read passively.

### `think_in_japanese_character_reading_aid_part4.html`

The Reading Aid lists characters that appear in the phrase pages.

It helps learners connect the phrase material to character recognition by showing:

- Character
- Romaji sound
- Type: hiragana, katakana, or kanji
- Frequency count
- Example phrase
- Example romaji
- Meaning
- Source part

The Kanji Hub uses this page conceptually as a seed source for the most relevant kanji.

### `think_in_japanese_part5_frequency_deck.html`

The Frequency Deck prioritizes characters by how often they appear in the phrase collection.

This supports the idea that learners should recognize the highest-value characters first instead of learning only by textbook order.

### `think_in_japanese_part6_90_day_plan.html`

The 90-Day Plan ties the entire portal together.

It breaks the learning path into phases such as:

- Survival Brain
- Daily Life Narration
- Social Survival
- Osaka / PR Mode
- Gaki Mode
- Reading Unlock

### `japanese_90_day_calendar_tracker.html`

The tracker provides a day-by-day schedule for study.

Core behavior:

- Shows scheduled study cards.
- Allows marking items complete.
- Allows deferring work.
- Stores progress locally where supported.
- Helps keep the study process structured instead of relying on memory or motivation alone.

---

## Theme System

The portal uses a shared theme system so pages feel consistent.

Current themes:

- Pixel Pastel v2
- Cream Garden
- Tokyo Night

The theme buttons write the selected theme to browser storage and apply a matching body class such as:

```text
theme-pixel
theme-garden
theme-night
```

Pages then use CSS overrides to adjust colors, contrast, borders, and readability for each theme.

When adding new pages, include the same theme switcher markup and load:

```html
<link href="pixel-theme-v2.css" rel="stylesheet" />
```

Also make sure custom cards, tables, buttons, and panels have theme-specific readability rules if needed.

---

## Language System

The project currently uses separate English and Spanish HTML pages.

Examples:

```text
index.html        -> English
index_es.html     -> Spanish
kana_dojo.html    -> English
kana_dojo_es.html -> Spanish
kanji_hub.html    -> English
kanji_hub_es.html -> Spanish
```

Each page includes navigation links for its own language and a language toggle to switch to the matching page in the other language.

When adding a new page:

1. Create the English version.
2. Create the Spanish version with `_es` in the filename.
3. Add both versions to the navigation menus.
4. Add a language toggle between the matching pages.
5. Update `sitemap.xml` if the page is public.

---

## Core JavaScript Patterns

The project intentionally avoids frameworks so the site remains easy to copy, inspect, and run offline.

Common patterns used across the site:

### Local data arrays

Pages such as Kana Dojo and Kanji Hub store learning content directly in JavaScript arrays or objects.

Example concept:

```javascript
const DATA = [
  {
    japanese: "今日は疲れた。",
    romaji: "Kyou wa tsukareta.",
    meaning: "I am tired today."
  }
];
```

This keeps pages portable and avoids needing a database.

### Render functions

Interactive pages usually generate cards, rows, or tiles using JavaScript render functions.

Typical flow:

```text
load data -> filter data -> group/sort data -> render HTML -> attach event handlers
```

### Filtering and searching

Search inputs usually normalize text to lowercase and compare against multiple fields such as:

- Japanese text
- Romaji
- Meaning
- Category
- Source

### Local storage

Where progress or preferences are saved, the site uses browser `localStorage`.

Typical use cases:

- Theme selection
- Calendar tracker progress
- Completion/deferred status
- Optional game/session settings

Because browser storage is local to the device and browser, progress is not synced across devices unless the user manually exports or copies data.

---

## Extending the Kana Dojo Word List

Kana Dojo can be expanded by adding more word entries to its local data or by using the included JSON-extension pattern where available.

A typical word entry should include:

```json
{
  "romaji": "neko",
  "kana": "ねこ",
  "translation": "cat",
  "type": "hiragana"
}
```

Recommended fields:

- `romaji`: prompt shown to the learner
- `kana`: expected kana answer
- `translation`: English or Spanish meaning
- `type`: hiragana or katakana

Keep entries short and practical for recognition practice.

---

## Extending the Kanji Hub

Kanji Hub can be expanded by adding records to `KANJI_DATA` and examples to the example bank.

A typical kanji entry includes:

```javascript
{
  rank: 1,
  kanji: "日",
  reading: "hi / nichi / kyou / ashita",
  meaning: "day; sun; Japan-related reading depending on context",
  word: "日本語で何て言うんだっけ？",
  romaji: "Nihongo de nan te iun dakke?",
  natural: "How do you say it in Japanese again?",
  mnemonic: "Tie 日 to a phrase you already know so the symbol has context.",
  bucket: "H/B/P/F readings",
  source: "Think in Japanese Core / Part 4",
  count: 13,
  tier: "core"
}
```

Recommended entry rules:

- Use real, common Japanese words or phrases.
- Prefer kanji that appear in the phrase pages first.
- Keep mnemonics tied to actual usage, not abstract symbol memorization only.
- Keep romaji consistent across entries.
- Avoid adding rare kanji placeholders just to inflate the deck size.
- When translating the Spanish version, translate `meaning`, `natural`, `mnemonic`, `bucket`, and `source` where appropriate.

---

## Sitemap

The repository includes `sitemap.xml` for public indexing.

Update the sitemap when:

- A new public page is added
- A page is renamed
- A language version is added
- A page is removed

For GitHub-only offline use, the sitemap is not required. For the live website, it helps search engines discover the portal pages.

---

## Accessibility and Readability Notes

Because the portal is visually themed, every theme needs to be checked for contrast.

When editing styles, test at least:

- Pixel Pastel v2
- Cream Garden
- Tokyo Night
- Desktop width
- Tablet width
- Phone width

Pay special attention to:

- Card text contrast
- Table text contrast
- Placeholder text
- Dropdown text
- Button hover states
- Footer spacing
- Horizontal overflow

---

## Development Guidelines

This project is meant to stay simple and portable.

Recommended guidelines:

- Keep pages static.
- Avoid external dependencies unless absolutely necessary.
- Do not require a build step.
- Do not require a backend.
- Keep local/offline use as a first-class feature.
- Keep English and Spanish navigation consistent.
- Update the sitemap when adding public pages.
- Test all themes after changing shared CSS.
- Test both language versions after changing navigation.

---

## Contributing

Contributions are welcome, especially:

- Additional Japanese study content
- Better kanji examples and mnemonics
- Spanish localization improvements
- Mobile usability improvements
- Accessibility and contrast fixes
- Additional kana and kanji exercises
- Better printable study materials
- New themes that remain readable

Please keep the project offline-friendly and avoid adding server requirements.

---

## License

- Code: MIT License
- Learning content: CC BY-NC 4.0
  
---

## Credits

Created by Edwin A. Rodriguez / ProgreTech.

Another tool from:

https://progretech.com

Inspired by:

- Japanese travel experiences
- Odaiba
- Rainbow Bridge
- Kagoshima
- Retro pixel-art games
- Spanish-to-Japanese learning bridges
- Phrase-first language learning
- Practical internal-monologue practice
