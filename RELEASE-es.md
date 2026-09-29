# Spanish lexicon pack v1

Structural lexicon for Spanish, for Word Garner and anything else that wants
it. Two files under two different licences, which is why they are two files.

| File | Compressed | On disk | Rows |
|---|---:|---:|---|
| `lexicon_es_grammar.db.gz` | 12.9 M | 35.4 M | 83793 lemmas, 690476 forms |
| `lexicon_es_ipa.db.gz` | 0.8 M | 2.1 M | 67973 pronunciations |

`lexicon_es_grammar.db` holds grammatical gender, the
part of speech of nouns that carry one, and a form table that resolves an
inflected word to its dictionary form. No irregular-form list yet: Word Garner
has no rules for which Spanish forms are regular, so none are singled out.

`lexicon_es_ipa.db` holds one phonemic
transcription per word.

## Licences

**`lexicon_es_grammar.db.gz` — CC0 1.0 Universal.** Derived from
[Wikidata Lexemes](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data),
a public-domain dedication. No attribution is required. It is given anyway.

**`lexicon_es_ipa.db.gz` — CC BY-SA 4.0.** Pronunciations extracted from
[Wiktionary](https://www.wiktionary.org) via
[wiktextract](https://github.com/tatuylonen/wiktextract), licensed
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

Modifications: reduced to one phonemic transcription per word and part of
speech; entries without a transcription were dropped.

**ShareAlike.** This derived database is itself CC BY-SA 4.0. The same notice
is stored inside the file, in its `licence` table.

## Verifying

`manifest.json` publishes SHA-256 for both the compressed and the
decompressed file, so a download can be checked either way round.
