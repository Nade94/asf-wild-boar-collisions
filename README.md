# African swine fever and wild boar road collisions in Catalonia

**Question:** after African swine fever (ASF) appeared in wild boar around Collserola (first case 28 Nov 2025) and the outbreak zone started culling and fencing, did wild boar road collisions drop in the affected area compared with the rest of Catalonia?

**Status:** work in progress. Step 1 done: data loaded, cleaned, and a first look at all of Catalonia.

## Data

Wild animal road collisions attended by the Mossos d'Esquadra, published on Transparència Catalunya (dataset [`ght6-dqp5`](https://analisi.transparenciacatalunya.cat/resource/ght6-dqp5.json)). 29,485 collisions, 2021 to June 2026, of which 19,038 involve wild boar.

## First look

![Monthly wild boar road collisions in Catalonia, Sep 2021 to Jun 2026](boar_monthly_catalonia.png)

January to June 2026 looks like the same months in earlier years (1,466 boar collisions, against 1,531 to 1,670 in 2022 to 2025). Collisions follow a clear seasonal pattern: lower from January to June and higher in autumn, with the mating season, hunting season and young boar dispersing.

For Catalonia as a whole there is no visible change after the outbreak. The outbreak zone is a small part of Catalonia, so a drop there would barely move the total. The next step is to compare the zone with the rest of Catalonia.

## Data quality log

- **API row limit:** the API returns only 1,000 rows by default, so `$limit=30000` loads all 29,486 rows.
- **"Total" row:** the year column had a "Total" summary row. It's removed, which leaves 29,485 rows.
- **Injury columns count people:** `ferits_lleus`, `ferits_greus` and `morts` count people, not animals. A blank means 0.
- **Labels:** the exact label for wild boar is `Ungulat (porc senglar)`. Some bird labels are duplicated.
- **2026 is partial:** the data stops at 30 June 2026.
- **2021 is not comparable before September:** from January to August 2021 there are only 21 to 55 boar collisions a month, then 306 in September and around 500 a month to December. January to August 2022 has 199 to 370 a month, and September matches in both years (306 vs 314), so the jump is likely a change in recording from September 2021, not fewer collisions. Monthly analysis starts in September 2021; yearly totals use 2022 to 2025 only.

## Next

1. Define the outbreak zone (municipalities inside the containment area).
2. Compare monthly collisions in the zone with the rest of Catalonia, same months across years.

## Files

- `01_load_explore.ipynb`: loading, cleaning, data quality checks, first chart.

Nade Cvetanovska · data analyst with veterinary domain expertise · [github.com/Nade94](https://github.com/Nade94)
