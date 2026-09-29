# German lexicon pack v3

Structural lexicon for German, for Word Garner and anything else that wants
it. Two files under two different licences, which is why they are two files.

| File | Compressed | On disk | Rows |
|---|---:|---:|---|
| `lexicon_de_grammar.db.gz` | 7.0 M | 19.5 M | 207,739 lemmas, 272,776 forms, 703 part-of-speech pairs |
| `lexicon_de_ipa.db.gz` | 797 K | 2.0 M | 51,495 pronunciations |

`lexicon_de_grammar.db` holds grammatical gender, the irregular forms —
`Buch`/`Bücher`, `gehen`/`ging` — and a form table that resolves an inflected
word to its dictionary form. Regular forms are deliberately absent: nobody
needs to be told that the plural of `Tisch` is `Tische`, and 82% of German
forms are dropped on that rule. Every noun keeps a row regardless, because
every German noun has a gender worth carrying.

`lexicon_de_ipa.db` holds one phonemic transcription per word.

## What changed in v3

The grammar file gains one table, `lemma_pos`: the kinds of word a lemma can
be, for the lemmas that can be more than one. German has few: it writes the noun `Essen` and the verb `essen` apart, and those are two lemmas. From Wikidata's lexical
categories, so it is CC0 like the rest of the file. Nothing else in either
file changed; the pronunciation file is republished unchanged so that both
halves share a version.

## What changed in v2

The extractor treated an entry as a mere inflected form if **any** of its
senses pointed at another word, rather than if all of them did. That
discarded 181 lemmas outright. German was barely affected — the recovered
words are mostly Austrian diminutives — but the same bug was removing
`child`, `foot` and `go` from the English pack, so both were rebuilt
together.

## Licences

**`lexicon_de_grammar.db.gz` — CC0 1.0 Universal.** Derived from
[Wikidata Lexemes](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data),
a public-domain dedication. No attribution is required. It is given anyway.

Modifications: reduced to the fields Word Garner displays; regular forms that
the app's own morphology rules derive were dropped.

**`lexicon_de_ipa.db.gz` — CC BY-SA 4.0.** Pronunciations extracted from
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
