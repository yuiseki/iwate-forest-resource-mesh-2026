# Raw profile of the 72 sheets that touch Iwate (whole sheets, before any cutting)

Source: G空間情報センター dataset `mesh_10` (全国森林資源メッシュ, zone X), sheets chosen by intersecting the sheet index with the Iwate boundary (KSJ N03). Run 2026-10-29; sha256 of each archive is in data/raw/20261029/MANIFEST.json (kept in the Hugging Face repo).

These counts cover the whole sheets, so they include cells of neighbouring prefectures and of the sea. The Iwate-only figures are in docs/iwate_profile.md.

- sheets: 72; rows: 46,980,617; layers: 72 geometry layers, one per file, named like the file; geometry type ids: {6: 46980617} (6 = MultiPolygon); invalid geometries: 0
- CRS: EPSG:6678; plane bbox x -20000 to 106500, y -150000 to 60000
- column sets: 1 distinct (林種, 森林簿樹種1, 森林簿樹種2, 森林簿樹種3, 林齢, 森林簿年月日, 樹冠高, レーザ解析樹種, 立木密度, 平均標高, 計測年月日, plus the GeoPackage fid)

| column | NULL rows | share of rows |
| --- | ---: | ---: |
| 林種 | 9,526,625 | 20.3% |
| 森林簿樹種1 | 9,525,350 | 20.3% |
| 森林簿樹種2 | 36,155,169 | 77.0% |
| 森林簿樹種3 | 42,102,228 | 89.6% |
| 林齢 | 9,526,625 | 20.3% |
| 森林簿年月日 | 9,525,292 | 20.3% |
| 樹冠高 | 46,980,617 | 100.0% |
| レーザ解析樹種 | 46,980,617 | 100.0% |
| 立木密度 | 46,980,617 | 100.0% |
| 平均標高 | 46,980,617 | 100.0% |
| 計測年月日 | 46,980,617 | 100.0% |

## Unique values of the text columns (all 72 sheets)

### 林種

| value | rows |
| --- | ---: |
| 天然林 | 20,285,228 |
| 人工林 | 15,331,695 |
| <NULL> | 9,526,625 |
| その他 | 824,560 |
| 伐採跡地 | 597,344 |
| 未立木地 | 396,475 |
| 竹林 | 18,690 |

### 森林簿樹種1

| value | rows |
| --- | ---: |
| 広葉樹 | 18,709,713 |
| <NULL> | 9,525,350 |
| スギ | 7,313,444 |
| マツ類 | 5,607,495 |
| カラマツ | 3,342,558 |
| その他 | 1,211,165 |
| 伐採跡地 | 568,790 |
| その他針葉樹 | 387,842 |
| ヒノキ類 | 177,464 |
| ヒバ | 105,268 |
| タケ | 18,690 |
| #N/A | 12,706 |
| エゾマツ | 132 |

### 森林簿樹種2

| value | rows |
| --- | ---: |
| <NULL> | 36,155,169 |
| 広葉樹 | 7,582,997 |
| マツ類 | 1,375,141 |
| スギ | 1,007,063 |
| カラマツ | 573,645 |
| その他針葉樹 | 126,148 |
| ヒバ | 123,689 |
| ヒノキ類 | 36,649 |
| タケ | 116 |

### 森林簿樹種3

| value | rows |
| --- | ---: |
| <NULL> | 42,102,228 |
| 広葉樹 | 3,338,554 |
| マツ類 | 670,625 |
| その他針葉樹 | 369,470 |
| ヒバ | 208,909 |
| スギ | 206,611 |
| カラマツ | 66,953 |
| ヒノキ類 | 17,267 |

### レーザ解析樹種

| value | rows |
| --- | ---: |
| <NULL> | 46,980,617 |

### 森林簿年月日

| value | rows |
| --- | ---: |
| 2024/4/1 | 20,890,277 |
| <NULL> | 9,525,292 |
| 2023/4/1 | 5,024,873 |
| 2020/4/1 | 3,087,627 |
| 2022/4/1 | 2,389,506 |
| 2019/4/1 | 1,701,999 |
| 2021/4/1 | 1,577,523 |
| 2023/3/31 | 1,469,071 |
| 2024/3/31 | 1,314,449 |

## Other findings

- 計測年月日 values other than NULL: {}
- The literal text `#N/A` as a value: 森林簿樹種1 12,706 rows, 森林簿樹種2 0 rows; kept as in the source.
- 林齢 is 0 in 1,776,044 rows besides the NULLs (9,526,625); whether 0 means an age of zero or an unknown age is not stated in the definition.
- 森林簿年月日 holds 8 dates, as text: 2019/4/1, 2020/4/1, 2021/4/1, 2022/4/1, 2023/3/31, 2023/4/1, 2024/3/31, 2024/4/1.
- No column separates 国有林 from 民有林 in the mesh; that attribute (民国別) is in the 森林計画対象森林レイヤ of Iwate (downloaded as well).
