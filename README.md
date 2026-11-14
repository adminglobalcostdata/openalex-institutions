# OpenAlex Institutions: 143,455 universities and labs

[![Apify Actor](https://img.shields.io/badge/Apify-Actor-1f6feb)](https://apify.com/phonic_lily/openalex-institutions) ![Licence](https://img.shields.io/badge/licence-CC0_1.0-blue) ![Records](https://img.shields.io/badge/records-143%2C455-green)

Search 143,455 research institutions from OpenAlex (snapshot 2026-10-14): universities, hospitals, companies, funders. Country, city, coordinates, ROR/Wikidata ids, works and citation counts, h-index, update year. CC0. Embedded data, pay per record.

## What you get
- **143,455 records**, each carrying its own `license` and `attribution` fields, ready to republish with the required credit.
- A **100-record free sample** in this repository: [`sample.jsonl`](sample.jsonl) and [`sample.csv`](sample.csv) (opens as a table on GitHub).
- The **full dataset** as a filterable API (JSON, CSV, Excel), no scraping, no login: [OpenAlex Institutions: 143,455 universities and labs on Apify](https://apify.com/phonic_lily/openalex-institutions).

## One record
```json
{
  "openalex_id": "I4210119613",
  "ror_id": "01x5f7a18",
  "name": "Byzantine Studies Association of North America",
  "type": "other",
  "status": "active",
  "country_code": "US",
  "country_name": "United States",
  "region": "New York",
  "city": "New York",
  "lat": 40.71592,
  "lon": -74.00523,
  "geonames_city_id": 5128581
}
```

## Quick start
Python:
```python
from apify_client import ApifyClient
client = ApifyClient('<YOUR_APIFY_TOKEN>')
run = client.actor('phonic_lily/openalex-institutions').call(run_input={'maxResults': 10})
for item in client.dataset(run['defaultDatasetId']).iterate_items():
    print(item)
```
Or from the command line:
```bash
curl -X POST 'https://api.apify.com/v2/acts/phonic_lily~openalex-institutions/run-sync-get-dataset-items?token=<YOUR_APIFY_TOKEN>' \
  -H 'Content-Type: application/json' -d '{"maxResults": 10}'
```
Pricing is pay-per-record on Apify (see the Actor page); the sample here is free.

## Fields
| Field | Description |
|---|---|
| `openalex_id` | OpenAlex institution id (I...). |
| `ror_id` | ROR identifier, null if none. |
| `name` | Display name. |
| `type` | OpenAlex institution type. |
| `status` | Record status in OpenAlex. |
| `country_code` | ISO 3166-1 alpha-2 country code. |
| `country_name` | Country name. |
| `region` | Region, null if unknown. |
| `city` | City. |
| `lat` | Latitude, decimal degrees. |
| `lon` | Longitude, decimal degrees. |
| `geonames_city_id` | GeoNames id of the city. |
| `homepage_url` | Homepage URL. |
| `acronyms` | Acronyms, comma separated. |
| `wikidata_id` | Wikidata Q-identifier. |
| `grid_id` | Legacy GRID identifier. |
| `wikipedia_url` | Wikipedia URL. |
| `works_count` | Number of works affiliated. |
| `cited_by_count` | Citations received by those works. |
| `h_index` | h-index of the institution. |
| `i10_index` | i10-index of the institution. |
| `mean_citedness_2yr` | Two-year mean citedness. |
| `updated_year` | Year of the last update of the record. |
| `updated_date` | Date of the last update of the record (YYYY-MM-DD). |
| `created_date` | Date the record was created (YYYY-MM-DD). |

## Data, licence and attribution
OpenAlex institutions entity, public snapshot of 2026-10-14 (https://openalex.s3.amazonaws.com/data/jsonl/institutions/manifest.json, record_count 143,455), the bulk equivalent of the /institutions API endpoint. Licence: the bucket LICENSE.txt is CC0 1.0 Universal, and https://help.openalex.org/access/overview states that all the data is free and open under CC0. Only organizations, no personal data. Counts (works, citations) are as of the snapshot and genuine zeros are kept; fields missing in the source are null, never 0.

**Licence:** CC0 1.0 (OpenAlex data)

**Attribution:** Source: OpenAlex (https://openalex.org), released under CC0 1.0. No attribution is legally required; crediting OpenAlex is appreciated.

Snapshot date: 2026-10-14. Empty values are `null`, never 0.

## Cite this dataset
GitHub's *Cite this repository* button reads [`CITATION.cff`](CITATION.cff).

## Feedback
Found an error or want a field added? Open an issue in this repository.
