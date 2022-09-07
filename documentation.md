---
layout: page
title: Documentation
permalink: /documentation/
---

## Documentation

### (Content: Holt) Separating the texts
In order to clean the inconsistently OCR-ed files for the pipe rolls I took several steps to deal with frontmatter, backmatter, and formatting concerns with the actual layout of the text.

#### Steps taken
For the Holt volume (roll years 1208-1209), I began wrestling with regular expressions (regex) that could look forward and back to handle line breaks and page breaks. Unfortunately, this was a rather poor application, as the formatting of the volume changes drastically between the editorial content of the (English prose) front matter (with footnotes), main Latin text (with variable English/Latin footnotes), and back matter. Between fiddling with batch-changing linebreaks and inconsistent application between the front matter and main text, I decided to separate the three portions manually to approach them separately. I then focused on the main Latin text.

#### Page breaks and footnotes
Once separated, the format of the main Latin text of the Holt volume was a bit easier to handle (Hall and Page's first volume are drastically different again based on formatting, language, and differing OCR quality; Page's second volume has yet to be scanned). For this, I aimed to primarily remove line breaks and page breaks before splitting the text into more functional parts which address accounts for each manor. To this end I followed the steps below:

- removed page headings on recto/verso pages with permutations of:
	- `\n THE PIPE ROLLS OF THE BISHOPRIC OF WINCHESTER \d+\n`
	- `\n\d+ THE PIPE ROLLS OF THE BISHOPRIC OF WINCHESTER\n` 
- removed inter-word line breaks:
	- `(?<=[a-z]) ?\n(?=[a-z])`
	- `-?\n(?=[a-z])`

It was at this point that I realized that the main text still had footnotes that needed to be addressed, which were irregularly constructed and numbered - specifically in regards to the number of entries on each page and their numbering (problematic partially due to small blotchy typefaces, sometimes-multi-column layout, and resultant poor OCR). This resulted in an attempt to excise them visually from the rest of the lines and spot-check/hand-edit a beginning/ending string:

- separated footnotes from bottom of Latin text with $$1. Bad OCR made this difficult, with a few hand-corrected interventions necessary:
	- `\n1 (?=[A-Z])`
	- `\n: (?=[A-Z])`
	- `\n* (?=[A-Z])`

I then went for broke and removed all line breaks completely. The intention was then to break out all the footnotes between the string `@@1` and `!###` (which could be done with ` @@1.+` at this point, but I wanted to be careful). This done and cleaned a bit based on some funky footnotes that escaped the `@@1` prefacing, I was able to generate a single "line" of text with over 200,000 columns. I was then able to break out lines per each manor by finding strings of multiple capital letters ` (?=[A-Z][A-Z][A-Z]+)` which was refined by removing false-positive lines with multiple capital-I characters (sometimes recognized from the Roman numerals, sometimes OCR issues with the Arabic numeral 11). This required a bit of hand-cleaning and double-checking with the original PDF manuscript to make sure Latin placenames were constructed correctly.

#### Reflection
I'm unsure if this is the best way forward for repetitive cleaning for the Hall (1208-1209) and Page () volumes. Hall will have the same problems with English/Latin, and though Page is entirely in English it is a worse scan with worse OCR. I now better understand that I can't ask regex to do undefined-length lookbehinds (which I was hoping would work for "all characters between the starting string of '@@1' and ending string of '!###' including line breaks" which would have prevented me from having to remove all line breaks). At this point I also want to break the files up even more into more discrete categories for better granularity. These categories would include several categories, including some that are not universal:
- Purchasia
- Liberatio
- Expensa
	- Expensa Manerii
	- Expensa Molendini
	- Expensa Forinseca
- Exitus Grangie
	- Exitus Grangie de Pevet
- Instaurum
- De Fine et Scutagio

It should be easy enough to break apart the lines in this document by a simple lookahead for these words, and then a quick touchup in OpenRefine to add blank columns where necessary for those manors missing the categories.

