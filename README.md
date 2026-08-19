# Iraq Administrative Divisions / العراق



## Overview

| Item | Details |
|------|---------|
| Governorate | 18 |
| District | 101 |
| Sub-district | 294 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/iq](https://openadmindata.org/iq/) |
| API | [openadmindata.org/api/iq](https://openadmindata.org/api/iq/) |
| National Anthem | [🎵 Listen & Download Iraq National Anthem MP3](https://onlygames.me/national-anthems/iq/) |

## Browse by Governorate

| # | Governorate | Districts | Sub-districts | Link |
|---|----|----|----|------|
| 1 | الانبار (Al-Anbar) | 7 | 20 | [Browse](divisions/al-anbar-iqg01/) |
| 2 | البصرة (Al-Basrah) | 7 | 18 | [Browse](divisions/al-basrah-iqg02/) |
| 3 | المثنى (Al-Muthanna) | 4 | 8 | [Browse](divisions/al-muthanna-iqg03/) |
| 4 | النجف (Al-Najaf) | 3 | 6 | [Browse](divisions/al-najaf-iqg04/) |
| 5 | القادسية (Al-Qadissiya) | 4 | 13 | [Browse](divisions/al-qadissiya-iqg05/) |
| 6 | السليمانية (Al-Sulaymaniyah) | 10 | 29 | [Browse](divisions/al-sulaymaniyah-iqg06/) |
| 7 | بابل (Babil) | 4 | 11 | [Browse](divisions/babil-iqg07/) |
| 8 | بغداد (Baghdad) | 7 | 21 | [Browse](divisions/baghdad-iqg08/) |
| 9 | ديالى (Diyala) | 6 | 21 | [Browse](divisions/diyala-iqg10/) |
| 10 | دهوك (Duhok) | 4 | 14 | [Browse](divisions/duhok-iqg09/) |
| 11 | اربيل (Erbil) | 6 | 21 | [Browse](divisions/erbil-iqg11/) |
| 12 | كربلاء (Kerbala) | 3 | 5 | [Browse](divisions/kerbala-iqg12/) |
| 13 | كركوك (Kirkuk) | 4 | 16 | [Browse](divisions/kirkuk-iqg13/) |
| 14 | ميسان (Maysan) | 6 | 12 | [Browse](divisions/maysan-iqg14/) |
| 15 | نينوى (Ninewa) | 9 | 28 | [Browse](divisions/ninewa-iqg15/) |
| 16 | صلاح الدين (Salah Al-Din) | 7 | 19 | [Browse](divisions/salah-al-din-iqg16/) |
| 17 | ذي قار (Thi Qar) | 5 | 18 | [Browse](divisions/thi-qar-iqg17/) |
| 18 | واسط (Wassit) | 5 | 14 | [Browse](divisions/wassit-iqg18/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-governorate.json](data/all-governorate.json) | JSON | All 18 governorate records |
| [all-district.json](data/all-district.json) | JSON | All 101 district records |
| [all-subdistrict.json](data/all-subdistrict.json) | JSON | All 294 sub-district records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-governorate.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-governorate.json", "utf-8"));
console.log(`Total: ${data.length} governorates`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=governorate, 2=district, 3=sub-district |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{governorate-slug}/
divisions/{governorate-slug}/{district-slug}/
```

Sub-districts are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-governorate links
- [Per-governorate data](docs/llms-full/) — Full data by governorate

## Citation

```
Iraq Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/iraq-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
