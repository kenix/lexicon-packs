# Word Garner lexicon packs — sources and licences

These files are data, not program code. They are published separately from the
Word Garner application binary and are downloaded by the app on request.

## Grammar packs — `lexicon_<lang>_grammar.db.gz`

Gender, irregular forms and an inflected-form → lemma table, derived from
**Wikidata Lexemes**, released under **CC0 1.0 Universal** (public domain
dedication).

- Source: https://www.wikidata.org/wiki/Wikidata:Lexicographical_data
- Licence: https://creativecommons.org/publicdomain/zero/1.0/
- Modifications: reduced to the fields Word Garner displays; regular forms that
  the app's own morphology rules can derive were dropped.

No attribution is required for CC0 material. It is given here anyway.

## Pronunciation packs — `lexicon_<lang>_ipa.db.gz`

Phonemic transcriptions (IPA) derived from **Wiktionary**, via the
**wiktextract** extraction of the Wiktionary dumps.

- Source: https://www.wiktionary.org
- Extraction tool: https://github.com/tatuylonen/wiktextract
- Licence: **CC BY-SA 4.0** — https://creativecommons.org/licenses/by-sa/4.0/
- Modifications: reduced to one phonemic transcription per word and part of
  speech; entries without a transcription were dropped.

**ShareAlike:** these derived pronunciation databases are themselves licensed
CC BY-SA 4.0. The same notice is stored inside each database, in its `licence`
table.

These files are distributed as plain release assets with no technological
protection measures applied, which is why they are not shipped inside the
app's signed store binary (CC BY-SA 4.0 §2(a)(5)(B)).
