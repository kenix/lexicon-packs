# Danish lexicon pack v2

Structural lexicon for Danish, for Word Garner and anything else that wants
it. Two files under two different licences, which is why they are two files.

| File | Compressed | On disk | Rows |
|---|---:|---:|---|
| `lexicon_da_grammar.db.gz` | 1.2 M | 3.0 M | 74375 lemmas, 32149 forms, 2354 part-of-speech pairs |
| `lexicon_da_ipa.db.gz` | 0.1 M | 0.2 M | 6475 pronunciations |

`lexicon_da_grammar.db` holds grammatical gender, the
part of speech of nouns that carry one, and a form table that resolves an
inflected word to its dictionary form, and the kinds of word each lemma can be
where it can be more than one (English "spar": noun, verb). No irregular-form list yet: Word Garner
has no rules for which Danish forms are regular, so none are singled out.

`lexicon_da_ipa.db` holds one phonemic
transcription per word.

## Licences

**`lexicon_da_grammar.db.gz` — CC0 1.0 Universal.** Derived from
[Wikidata Lexemes](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data),
a public-domain dedication. No attribution is required. It is given anyway.

**`lexicon_da_ipa.db.gz` — CC BY-SA 4.0.** Pronunciations extracted from
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
