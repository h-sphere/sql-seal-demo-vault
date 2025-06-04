
> [!INFO] Pie Chart Example
> Code below shows how easy you can create PieChart out of your data. Change data in your table and see chart updating automatically.

| Category      | Amount |
| ------------- | ------ |
| Rent          | 500    |
| Groceries     | 350    |
| Entertainment | 1050   |
| Repairs       | 1200   |
| Utilities     | 300    |
```sqlseal
TABLE finances = table(0)

CHART {
	series: [{
		type: 'pie'
	}]
}
SELECT * FROM finances
```


## Doughnut

```sqlseal
TABLE finances = table(0)

CHART {
	series: [{
		type: 'pie',
		radius: ['40%', '70%']
	}]
}
SELECT * FROM finances
```

## Nightingale (Rose Chart)

```sqlseal
TABLE finances = table(0)

CHART {
	series: [{
		type: 'pie',
		roseType: 'area'
	}]
}
SELECT * FROM finances
```
