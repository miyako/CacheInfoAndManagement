# キャッシュの情報と管理

Cache information and management (4D Technical Note 25-02): Japanese edition.

4Dのキャッシュは、作成・更新されたデータや、頻繁にクエリされるデータを保持するバッファーです。本テクニカルノートでは、4Dにおけるキャッシュ設定の変遷を振り返り、4Dエンジンによるキャッシュの管理方法を説明したうえで、キャッシュのサイズやフラッシュ頻度を調整する設定、キャッシュの値を取得・操作するためのコマンド（GET MEMORY STATISTICS、Get database measures、Cache infoなど）、管理ウィンドウや4D_Info_Reportによる監視、ORDAキャッシュについて解説します。本テクニカルノートにデモプロジェクトはありません。

## Download

| | |
|---|---|
| PDF (Japanese) | [25-02_CacheInfoAndManagement_ja.pdf](https://github.com/miyako/CacheInfoAndManagement/releases/latest/download/25-02_CacheInfoAndManagement_ja.pdf) |
| Original (English) | `document/25-02_CacheInfoAndManagement.pdf` |

## Differences from the original

- 12 screenshots (figures 8, 9, 12–14, 16–22) are replaced with screenshots of the Japanese 4D UI. Figure 8 now shows 4D Server 21 R4, so the sentence before it gives the cache usage shown there (18%) instead of the original "100.00 MB".
- UI labels in the text follow the Japanese 4D UI (e.g. 「起動時にキャッシュサイズを計算」, 「ユーザー設定を有効にする」). The refresh option "Frequently" is not localised in the UI and stays in English.
- Two paragraphs that appear twice in the original, as a first draft and a reworded version (in "A brief history of the Cache settings in 4D" and "What can be retained"), are translated once, from the reworded version.
- The unfinished phrase "The real values" in the GET MEMORY STATISTICS section is left out.
- The cover shows only the title and the author.
- Parameter and value lists are typeset as tables, and the "Note:" paragraphs as shaded notes.
- Code (4D, XML, JSON) is unchanged, including comments.

## Editing and rebuilding

The PDF is generated from plain-text sources. Edit them and run `make`.

| File | What |
|---|---|
| `src/ja.md` | Translated body text. **Don't touch code blocks** (`make check` verifies them). |
| `figures/fig-NN-ja.png` | Japanese screenshots, used through `"replace"` in `figures/layout/fig-NN.json` |
| `figures/layout/fig-NN.json` | Per-figure settings: `"localize"`, `"replace"`, `"replace_width_pt"` (printed width of the replacement) |
| `glossary.md` | Terminology |

```sh
make            # check → figures → build/25-02_CacheInfoAndManagement_ja.pdf
make check      # code blocks unchanged, figure references complete
make review     # contact sheets of the figures (build/contact-N.png)
make release-assets
```

Requirements: Python 3, Google Chrome, CJK fonts, and Tesseract (only needed for re-extraction).
See the [localisation template](https://github.com/miyako/4d-technote-localisation-template) for the full workflow.

## Credits

- Original: Thomas SCHLUMBERGER, Technical Support Engineer, 4D France. Technical Note 25-02.
- Produced with [4d-technote-localisation-template](https://github.com/miyako/4d-technote-localisation-template) and GitHub Copilot.
