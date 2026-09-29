# Chinese lexicon pack v2

Structural lexicon for Chinese, covering both Simplified and Traditional. Two
files under two different licences, which is why they are two files.

| File | Compressed | On disk | Rows |
|---|---:|---:|---|
| `lexicon_zh_grammar.db.gz` | 4.6 M | 8.4 M | 198,367 script mappings, 3,360 part-of-speech pairs |
| `lexicon_zh_ipa.db.gz` | 2.8 M | 6.8 M | 263,431 pinyin readings |

## What changed in v2

The grammar file gains one table, `lemma_pos`: the kinds of word a lemma can
be, for the lemmas that can be more than one. From Wikidata's lexical
categories, so it is CC0 like the rest of the file. Nothing else in either
file changed; the pronunciation file is republished unchanged so that both
halves share a version.

## What is different about Chinese

**The readings are pinyin, not IPA.** Mandarin pinyin with tone marks —
`中国` → `Zhōngguó`, `从容` → `cóngróng`. IPA is unreadable to most people
learning Chinese and pinyin is the thing they actually say, so it is what the
pack carries. Wiktionary holds a dozen romanisations per word across every
dialect it covers; this is Standard Mandarin only.

**Both scripts work.** Wiktionary keys its Chinese entries on the Traditional
spelling, so 馬 has everything and 马 has nothing. 108,477 Simplified
spellings are resolved to their Traditional entry, so a capture in either
script finds the same reading. 马, 龙 and 爱 answer exactly as 馬, 龍 and 愛
do.

**The grammar pack holds no grammar.** Chinese has no plural, gender or
tense, so there is nothing of that kind to store and none is stored — a
gender letter under a Chinese word would be a bug. What the file actually is
is a 198,367-row script conversion table, which is what lets a capture
resolve at all, and since v2 the kinds of word a lemma can be.

**Single characters are covered.** A single character is the commonest thing
a learner of Chinese captures, and a dictionary files it under neither noun
nor verb. 30,014 of them are included, along with phrases and interjections —
你好 is `nǐ hǎo`.

## Licences

**`lexicon_zh_grammar.db.gz` — CC0 1.0 Universal.** Derived from
[Wikidata Lexemes](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data),
a public-domain dedication. No attribution is required. It is given anyway.

**`lexicon_zh_ipa.db.gz` — CC BY-SA 4.0.** Readings extracted from
[Wiktionary](https://www.wiktionary.org) via
[wiktextract](https://github.com/tatuylonen/wiktextract), licensed
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

Modifications: reduced to one Standard Mandarin pinyin reading per word and
part of speech; other dialects and romanisations were dropped, as were
entries with no reading.

**ShareAlike.** This derived database is itself CC BY-SA 4.0. The same notice
is stored inside the file, in its `licence` table.

These are plain release assets with no technological protection measures
applied, which is why the reading file is **not** shipped inside a signed app
binary — CC BY-SA 4.0 §2(a)(5)(B).

## Verifying

`manifest.json` publishes SHA-256 for both the compressed and the
decompressed file, so a download can be checked either way round.
