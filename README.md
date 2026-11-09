# Print Listing Kit

Turn a finished 3D model into listings that get found and printed successfully: a title and tags people actually search, a description that sells it and sets expectations, the settings that worked, a fair price, the photos to take, and a README for the download. One kit covers every marketplace the person sells on.

**What you get:** Writes ready-to-paste listings for selling or sharing a 3D print model file on marketplaces such as Etsy, Printables, MakerWorld, Cults3D and Thangs - titles, descriptions, tags, print settings, assembly notes, license, price based on comparable models, a photo shot list and a download README - and checks titles and tags against each marketplace's limits with a script. Flags trademark and character risks and AI-disclosure rules.

Made by Beautiful Engine · [beautifulengine.com](https://www.beautifulengine.com) · [Questions or ideas? Open an issue](https://github.com/BeautifulEngine/print-listing-kit/issues/new)

## Install

### Claude app (web or desktop)

1. Download **[print-listing-kit.zip](print-listing-kit.zip)** from this repo (open the file, then use the download button). Don't unzip it.
2. Turn on **Settings > Capabilities > "Code execution and file creation"**.
3. Go to **Customize > Skills**, click **+**, then **+ Create skill > Upload a skill**, and upload the zip.
4. Start a new chat and ask in plain words. Claude picks the skill up on its own.

> GitHub's green "Code > Download ZIP" button won't work for this; it wraps everything in an extra folder. Use `print-listing-kit.zip`.

### Claude Code

As part of the Beautiful Engine collection (you get updates and the other skills):

```bash
claude plugin marketplace add BeautifulEngine/skills
claude plugin install beautiful-engine@beautiful-engine
```

Then use `/beautiful-engine:print-listing-kit`, or ask in plain words. Or install just this one:

```bash
git clone https://github.com/BeautifulEngine/print-listing-kit.git
mkdir -p ~/.claude/skills && cp -r print-listing-kit/print-listing-kit ~/.claude/skills/
```

Then use `/print-listing-kit`.

## Usage

```
/print-listing-kit <model name> [marketplaces] [free | paid] [price]
```

Attach photos, renders, the STL or 3MF (or a slicer screenshot), and any notes. Plain requests work too:

- "Listing kit for my modular hex planter. Selling on Etsy and Printables (free there)."
- "Write the MakerWorld listing for this articulated dragon. Printed on a Bambu H2D in PLA."
- "What should I charge for this STL bundle of 12 cable clips?"
- "Rewrite my Etsy listing; it's not getting views." (paste it)

Default marketplaces: Etsy, Printables, MakerWorld and Cults3D. Say which ones you use to narrow it.

## When Claude uses it

Someone wants to list, sell, upload or price an STL or 3MF model, write a 3D model description, or set up a 3D print file shop.

## How it works

```
print-listing-kit/
├── SKILL.md
├── assets/  base.css, deck.css, listing-kit-template.md
├── scripts/  audit.js, contact_sheet.py, fonts.py, listing_check.py, render.cjs, render.py, tokens.py
├── references/  rendering.md
```

Listings are written from the search terms and comparable models Claude finds on each marketplace, then checked by `listing_check.py` against title and tag limits and your list of trademark terms before you paste them.

## Works well with

- [Build Spec](https://github.com/BeautifulEngine/build-spec)
- [Brand Snapshot](https://github.com/BeautifulEngine/brand-snapshot)
- [All Beautiful Engine skills](https://github.com/BeautifulEngine/skills)

## Made by Beautiful Engine

Print Listing Kit is made by [Beautiful Engine](https://www.beautifulengine.com), a creative studio in Los Angeles working across brand, experiential and interactive design.

- **Website:** [beautifulengine.com](https://www.beautifulengine.com)
- **Questions, ideas, or something broke?** [Open an issue](https://github.com/BeautifulEngine/print-listing-kit/issues/new) and describe what you asked for and what happened.

This repo is published from [BeautifulEngine/skills](https://github.com/BeautifulEngine/skills); changes are made there and copied here.

## License

MIT. See [LICENSE](LICENSE).

