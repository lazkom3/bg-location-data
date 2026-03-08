# Bulgarian Addresses Database

Comprehensive database of Bulgarian addresses with postal codes and GPS coordinates.

## Data Source

- **Postal Codes & GPS:** [bgpostcode.com](https://bgpostcode.com/) - 5,338 settlements
- **Addresses:** Bulgarian addresses with streets, neighborhoods, villages, and settlements

## Files

| File | Format | Description |
|------|--------|-------------|
| `bulgarian_addresses_with_coords.csv` | CSV | Main data file with all columns |
| `bulgarian_addresses.json` | JSON | JSON array of all addresses |
| `bulgarian_addresses.xml` | XML | XML format of all addresses |
| `bulgarian_addresses_mysql.sql` | MySQL | MySQL INSERT statements |
| `bulgarian_addresses_postgresql.sql` | PostgreSQL | PostgreSQL INSERT statements |
| `bulgarian_addresses.db` | SQLite | SQLite database |

## Database Schema

### Columns

| Column | Type | Description |
|--------|------|-------------|
| `region` | String | Administrative region (oblast) |
| `city` | String | City/town name |
| `street` | String | Street name |
| `neighborhood` | String | Neighborhood name |
| `settlement` | String | Settlement/village name |
| `type` | String | Address type: city, street, neighborhood, village, settlement, mahalla |
| `postal_code` | String | 4-digit Bulgarian postal code |
| `lat` | Float | Latitude (Bulgaria: 41-44.5) |
| `lng` | Float | Longitude (Bulgaria: 22-29) |

## Statistics

- **Total Records:** 24,010
- **Records with Coordinates:** 22,900 (95.4%)
- **Settlement Types:**
  - street: 14,372
  - village: 4,330
  - neighborhood: 2,719
  - settlement: 1,230
  - mahalla: 1,106
  - city: 253

## Usage

### CSV
```python
import pandas as pd
df = pd.read_csv('bulgarian_addresses_with_coords.csv')
```

### JSON
```python
import json
with open('bulgarian_addresses.json', 'r') as f:
    data = json.load(f)
```

### SQLite
```python
import sqlite3
conn = sqlite3.connect('bulgarian_addresses.db')
cursor = conn.cursor()
cursor.execute("SELECT * FROM bulgarian_addresses LIMIT 10")
```

### MySQL
```bash
mysql -u user -p database_name < bulgarian_addresses_mysql.sql
```

### PostgreSQL
```bash
psql -U user -d database_name < bulgarian_addresses_postgresql.sql
```

## Coordinate System

- **Latitude:** 41.0 - 44.5 (Bulgaria)
- **Longitude:** 22.0 - 29.0 (Bulgaria)

## License

Data is sourced from publicly available information.

## Contact

For issues or questions, please open a GitHub issue.
