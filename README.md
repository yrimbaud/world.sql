# World Database Updated (2024-2025)

This repository contains an updated version of the MySQL "world" sample database. The data has been refreshed to reflect the geopolitical and demographic situation as of December 2025.

## Summary of Changes

1. **Heads of State** - 207 updates to reflect current world leaders
2. **Country Populations** - 79 countries updated with 2024-2025 UN estimates
3. **City Populations** - 120 major cities updated with current figures
4. **New Countries** - 4 countries added (created since 2000)
5. **New Cities** - 10 cities added for the new countries
6. **Country Removals** - Yugoslavia removed (replaced by Serbia and Montenegro)
7. **Country Renames** - East Timor → Timor-Leste, Czechia, North Macedonia, Eswatini, Türkiye
8. **Government Changes** - Barbados updated to Republic (became republic in 2021)

## Detailed Changes

### Heads of State (207 updates)

All heads of state have been updated to reflect leaders in office as of 2024-2025. Notable examples:

- Elisabeth II → Charles III (United Kingdom and Commonwealth realms)
- George W. Bush → Donald Trump (United States and territories)
- Jacques Chirac → Emmanuel Macron (France and territories)
- Javier Milei (Argentina)
- Lula da Silva (Brazil)
- Naruhito (Japan)
- Frederik X (Denmark)

### Country Populations (79 updates)

Populations have been updated with 2024-2025 UN estimates. Examples:

| Country | Old Value | New Value |
|---------|-----------|-----------|
| India | 1,013,662,000 | 1,440,000,000 |
| China | 1,277,558,000 | 1,410,000,000 |
| United States | 278,357,000 | 340,000,000 |
| France | 59,225,700 | 68,500,000 |
| Germany | 82,164,700 | 84,000,000 |
| United Kingdom | 59,623,400 | 68,000,000 |
| Japan | 126,714,000 | 123,000,000 |

### City Populations (120 updates)

Major world cities have been updated with current population figures. Examples:

| City | Old Value | New Value |
|------|-----------|-----------|
| Tokyo | 7,980,230 | 13,960,000 |
| Delhi | 7,206,704 | 16,800,000 |
| Shanghai | 9,696,300 | 24,900,000 |
| New York | 8,008,278 | 8,300,000 |
| Paris | 2,125,246 | 2,160,000 |
| London | 7,285,000 | 9,000,000 |

### New Countries (4 additions)

| Code | Country | Independence | Population |
|------|---------|--------------|------------|
| SSD | South Sudan | 2011 | 11,400,000 |
| MNE | Montenegro | 2006 | 620,000 |
| SRB | Serbia | 2006 | 6,650,000 |
| XKX | Kosovo | 2008 | 1,870,000 |

### New Cities (10 additions)

| City | Country | Population |
|------|---------|------------|
| Juba | South Sudan | 450,000 |
| Malakal | South Sudan | 160,000 |
| Wau | South Sudan | 150,000 |
| Podgorica | Montenegro | 190,000 |
| Niksic | Montenegro | 72,000 |
| Belgrade | Serbia | 1,400,000 |
| Novi Sad | Serbia | 380,000 |
| Nis | Serbia | 260,000 |
| Pristina | Kosovo | 210,000 |
| Prizren | Kosovo | 180,000 |

### Removed Countries

- **Yugoslavia (YUG)** - Dissolved; replaced by Serbia and Montenegro

### Renamed Countries

| Old Name | New Name | Code |
|----------|----------|------|
| East Timor | Timor-Leste | TLS |
| Czech Republic | Czechia | CZE |
| Macedonia | North Macedonia | MKD |
| Swaziland | Eswatini | SWZ |
| Turkey | Türkiye | TUR |

## Prerequisites

* MySQL 5.7+ or MariaDB 10.3+
* A MySQL client (command line, MySQL Workbench, phpMyAdmin, etc.)

## How to Use

1. **Clone the repository**
    - Open Terminal
    - Navigate to the directory where you want to clone the repository
    - Run `git clone https://github.com/yrimbaud/world.sql.git`
    - Navigate into the cloned repository with `cd world-database-updated`

2. **Import the database**
    - Using command line: `mysql -u your_username -p < world_2025.sql`
    - Using MySQL Workbench: File → Open SQL Script → Select the file → Execute

3. **Verify the import**
    - Connect to your MySQL server
    - Run `USE world;`
    - Run `SELECT * FROM country WHERE Code = 'SSD';` to verify South Sudan was added

## File Structure

```
world.sql/
├── README.md
├── world_2025.sql    # Complete database with all updates
└── world_2005.sql    # Original database (for reference)
```

## Database Schema

The database contains three tables:

- **country** - 243 countries with details (code, name, continent, region, population, head of state, etc.)
- **city** - 4,089 cities with population data
- **countrylanguage** - Languages spoken in each country with percentage of speakers

## Troubleshooting

If you encounter any issues while importing the database, double check that:

* You have MySQL or MariaDB installed and running
* You have sufficient privileges to create databases and tables
* The SQL file is not corrupted (check file size)
* Your MySQL version supports the syntax used

If you continue to encounter issues, feel free to open an issue on this GitHub repository.

## Data Sources

- Population data (United Nations World Population Prospects - 2024 Revision)
- Heads of state (Wikipedia, UN Protocol and Liaison Service)
- City populations (Various national statistics offices)

## License

This database is provided for educational purposes. The original MySQL world database is freely available from MySQL. The updates in this repository are provided without warranty.

You are free to use, modify, and distribute this database without attribution.
