# Documentation of jsonl ingestion to pgAdmin4
- In pgAdmin create a database
![create db](../assets/a.png)

- Name your database.
![name db](../assets/b.png)

- Navigate to `Schemas` -> `Tables`
- ![create table ](../assets/c.png)
![name table](../assets/d.png)

- ![e](../assets/e.png)
- In this table:
    - In the new created table:
````
CREATE TABLE IF NOT EXISTS market_table(
	id BIGSERIAL PRIMARY KEY,
	ingested_at TIMESTAMPTZ DEFAULT now(),
	raw_market_data JSONB NOT NULL
	);
```
- Execute Script
- ![g](../assets/g.png)

- Open PSQL Tool
![psql tool](../assets/h.png)

In the opened terminal:
- Inside the database: market_test=# 
- write: `\encoding`
    - expected output: `WIN1252`

- write: `\encoding UTF8`
- write: `\copy market_table(raw_market_data) FROM 'C:\Users\adelo\de25\swedish_tech_labor_market\data\2
025_enriched.jsonl' WITH(FORMAT csv, DELIMITER E'\x1f', QUOTE E'\x01', ESCAPE E'\x02');`
    - Expected output: `COPY 121343`
    - Meaning: 121343 rows are copied successfully.

## Validate the copy
- Copy the last id of the very last row in pgAdmin
- ![validate](../assets/i.png)
- Open Vscode with the Json file, CTRL + H, regex and paste the unique id and make sure it exists in the last row ()