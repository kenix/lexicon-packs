# English lexicon pack v2

Structural lexicon for English, for Word Garner and anything else that wants
it. Two files under two different licences, which is why they are two files.

| File | Compressed | On disk | Rows |
|---|---:|---:|---|
| `lexicon_en_grammar.db.gz` | 15.2 M | 32.3 M | 29,622 lemmas, 617,216 forms, 15,156 part-of-speech pairs |
| `lexicon_en_ipa.db.gz` | 1.2 M | 2.9 M | 92,261 pronunciations |

`lexicon_en_grammar.db` holds the irregular forms — `child`/`children`,
`go`/`went`/`gone`, `good`/`better`/`best` — and a form table that resolves an
inflected word to its dictionary form. Regular forms are deliberately absent:
nobody needs to be told that the plural of `cat` is `cats`, and dropping them
is what keeps the file this size. 29,622 lemmas is not thin coverage; it is
the count of English words with something irregular about them.

`lexicon_en_ipa.db` holds one phonemic transcription per word.

## What changed in v2

The grammar file gains one table, `lemma_pos`: the kinds of word a lemma can
be, for the lemmas that can be more than one — `spar` is a noun and a verb, `light` an adjective, adverb, noun and verb. From Wikidata's lexical
categories, so it is CC0 like the rest of the file. Nothing else in either
file changed; the pronunciation file is republished unchanged so that both
halves share a version.

## Licences

**`lexicon_en_grammar.db.gz` — CC0 1.0 Universal.** Derived from
[Wikidata Lexemes](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data),
a public-domain dedication. No attribution is required. It is given anyway.

Modifications: reduced to the fields Word Garner displays; regular forms that
the app's own morphology rules derive were dropped.

**`lexicon_en_ipa.db.gz` — CC BY-SA 4.0.** Pronunciations extracted from
[Wiktionary](https://www.wiktionary.org) via
[wiktextract](https://github.com/tatuylonen/wiktextract), licensed
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

Modifications: reduced to one phonemic transcription per word and part of
speech; entries without a transcription were dropped.

**ShareAlike.** This derived database is itself CC BY-SA 4.0. The same notice
is stored inside the file, in its `licence` table.

These are plain release assets with no technological protection measures
applied, which is why the pronunciation file is **not** shipped inside a
signed app binary — CC BY-SA 4.0 §2(a)(5)(B).

## Verifying

`manifest.json` publishes SHA-256 for both the compressed and the
decompressed file, so a download can be checked either way round.
