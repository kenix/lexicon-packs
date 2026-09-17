# Lexicon packs

Structural lexicon data for language-learning apps: grammatical gender, the
irregular forms a learner has to memorise, a table resolving an inflected
word back to its dictionary form, and phonemic transcriptions.

Published as GitHub Release assets, one release per language. **The data is
not in this repository** — a release asset can be replaced, while a 20 MB
binary in the history is in every clone for ever. What is here is the text
that defines a release.

| File | What it is |
|---|---|
| `manifest.json` | Which release is current per language, with sizes and checksums |
| `ATTRIBUTION.md` | Sources and licences for every pack |
| `RELEASE-<lang>.md` | The notes published with that language's release |

## Using it

`manifest.json` is the entry point, served from GitHub Pages so it can change
without cutting a release:

```
https://kenix.github.io/lexicon-packs/manifest.json
```

It names each language's current release tag, from which the asset URL
follows:

```
https://github.com/kenix/lexicon-packs/releases/download/<release>/<file>
```

Both a compressed and a decompressed SHA-256 are published, so a download can
be verified either way round.

Do not poll the GitHub API to discover releases — unauthenticated it allows
60 requests per hour per IP, which collapses behind carrier NAT.

## Two files per language, because two licences

**`lexicon_<lang>_grammar.db.gz` — CC0 1.0.** Gender, irregular forms and the
form table, from [Wikidata
Lexemes](https://www.wikidata.org/wiki/Wikidata:Lexicographical_data). Public
domain; no attribution required, and given anyway.

**`lexicon_<lang>_ipa.db.gz` — CC BY-SA 4.0.** Pronunciations from
[Wiktionary](https://www.wiktionary.org) via
[wiktextract](https://github.com/tatuylonen/wiktextract).

They are not merged, and must not be: merging would put the stricter licence
on both. The pronunciation packs are also why these are downloads rather than
bundles — CC BY-SA 4.0 §2(a)(5)(B) forbids applying technological protection
measures, and a signed app store binary is wrapped.

See `ATTRIBUTION.md` for the full notice, which also travels inside each
database in its `licence` table.

## What is deliberately absent

Regular forms. Nobody needs telling that the plural of `cat` is `cats` or of
`Tisch` is `Tische`; only what the language's own rules fail to predict is
stored. That is what keeps the files this size, and it is why a language's
lemma count is the count of its irregular words rather than of its
vocabulary.
