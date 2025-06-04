> [!INFO] Simple Bar Chart Example
> You can visualise any data stored in your vault. In this case we are visualising creation date of the files.

```sqlseal
CHART {
	xAxis: {
		type: 'category'
	},
	yAxis: {},
	series: [{
	type: 'bar',
	}]
}
SELECT
	strftime("%Y-%m-%d", created_at) as created_date,
	COUNT(*) as count
FROM files
GROUP BY created_date
ORDER BY created_date
```



| Date       | Distance |
| ---------- | -------- |
| 2025-05-01 | 40.4     |
| 2025-05-02 | 34.43    |
| 2025-05-03 | 43.53    |
| 2025-05-04 | 50.23    |
```sqlseal
TABLE t = table(0)
CHART {
	xAxis: {
		type: 'category'
	},
	yAxis: {},
	series: [
		{ type: 'bar' }
	]
}
SELECT * FROM t
```
| Date       | Biked | Walked |
| ---------- | ----- | ------ |
| 2025-05-01 | 40.4  | 20.4   |
| 2025-05-02 | 34.43 | 10.4   |
| 2025-05-03 | 43.53 | 17.53  |
| 2025-05-04 | 50.23 | 3.43   |

```sqlseal
TABLE t = table(1)
CHART {
	xAxis: {
		type: 'category'
	},
	yAxis: {},
	legend: { show: true },
	series: [
		{
			type: 'bar', 
			encode: { y: 'walked' },
			name: 'Walked'
		},
		{
			type: 'bar', 
			encode: { y: 'biked' },
			name: 'Biked'
		}
	]
}
SELECT * FROM t
```
