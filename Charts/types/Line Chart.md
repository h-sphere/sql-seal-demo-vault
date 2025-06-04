
| Date | s1  | s2  |
| ---- | --- | --- |
| 2024 | 200 | 150 |
| 2025 | 300 | 200 |
| 2026 | 400 | 340 |
| 2027 | 150 | 405 |
| 2028 | 305 | 300 |

```sqlseal
TABLE data = table(0)
CHART 
{
	xAxis: { type: 'category' },
	yAxis: { },
	legend: { show: true },
	series: [{ type: 'line' }, { type: 'line' }]
}
SELECT * FROM data
```

The series gets automatically mapped in order. If you want to specify different order, you can reorder columns returned in SQL query or, for more control specify dimensions for each series:

```sqlseal
CHART 
{
	xAxis: { type: 'category' },
	yAxis: { },
	series: [{ type: 'line', gridIndex: 1 }, { type: 'line', gridIndex: 2 }]
}
SELECT date, s2, s1 FROM data 
-- the order is "wrong", we need to reorder it for the query
```

For even more control, use "encode" object of the series:
```sqlseal
CHART 
{
	xAxis: { type: 'category' },
	yAxis: { },
	series: [
		{
			type: 'line',
			encode: {
				x: 'date',
				y: 's1'
			}
		},
		{
			type: 'line',
			encode: {
				x: 'date',
				y: 's2'
			}
		}
	]
}
SELECT date, s2, s1 FROM data 
-- the order is "wrong", we need to reorder it for the query
```

It's also a good way to specify for example data for tooltip:

| Data | Value | Description            |
| ---- | ----- | ---------------------- |
| 2025 | 150   | This is value for 2025 |
| 2026 | 300   | This is value for 2026 |
| 2027 | 100   | This was a bad year    |
| 2028 | 300   | And back up            |

```sqlseal
TABLE d2 = table(1)
CHART
{
	xAxis: { type: 'category' },
	yAxis: { },
	tooltip: { },
	series: [{
		type: 'line',
		encode: {
			tooltip: 'description'
		}
	}]
}
SELECT * FROM d2
```
