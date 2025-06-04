
# Data
| Title                              | Wordcount | Rating |
| ---------------------------------- | --------- | ------ |
| War and Peace                      | 587000    | 4.1    |
| Don Quixote                        | 345000    | 4.2    |
| Les Misérables                     | 531000    | 4.4    |
| The Count of Monte Cristo          | 375000    | 4.6    |
| Anna Karenina                      | 349000    | 4.3    |
| Crime and Punishment               | 211000    | 4.2    |
| Pride and Prejudice                | 122000    | 4.5    |
| Moby Dick                          | 206000    | 3.9    |
| Great Expectations                 | 183000    | 4.0    |
| Jane Eyre                          | 183000    | 4.4    |
| The Brothers Karamazov             | 364000    | 4.3    |
| Middlemarch                        | 316000    | 4.0    |
| The Great Gatsby                   | 47000     | 4.2    |
| Wuthering Heights                  | 107000    | 4.1    |
| One Hundred Years of Solitude      | 144000    | 4.3    |
| To Kill a Mockingbird              | 100000    | 4.6    |
| The Odyssey                        | 123000    | 4.0    |
| The Divine Comedy                  | 112000    | 4.1    |
| The Picture of Dorian Gray         | 78000     | 4.2    |
| Frankenstein                       | 75000     | 4.0    |
| The Adventures of Huckleberry Finn | 110000    | 4.0    |
| The Scarlet Letter                 | 63000     | 3.8    |
| Little Women                       | 183000    | 4.3    |
| The Tale of Genji                  | 330000    | 4.0    |
| The Grapes of Wrath                | 169000    | 4.1    |
| David Copperfield                  | 358000    | 4.2    |
| Emma                               | 155000    | 4.0    |
| The Three Musketeers               | 228000    | 4.3    |
| The Canterbury Tales               | 112000    | 3.9    |
| The Red and the Black              | 176000    | 4.0    |
| Ulysses                            | 265000    | 3.5    |
| Finnegans Wake                     | 169000    | 3.2    |
| Ethan Frome                        | 34000     | 3.4    |
| The Sound and the Fury             | 96000     | 3.6    |
| Paradise Lost                      | 80000     | 3.7    |
| The Old Man and the Sea            | 27000     | 3.8    |
| The Sun Also Rises                 | 67000     | 3.7    |
| Heart of Darkness                  | 38000     | 3.4    |
| The Awakening                      | 45000     | 3.6    |
| The Castle                         | 198000    | 3.5    |
| The Trial                          | 84000     | 3.7    |
| Beowulf                            | 45000     | 3.5    |
| Jude the Obscure                   | 151000    | 3.6    |
| The Portrait of a Lady             | 207000    | 3.7    |
| The Wings of the Dove              | 168000    | 3.3    |
| Lord Jim                           | 132000    | 3.4    |
| The Good Soldier                   | 87000     | 3.6    |
| The Rainbow                        | 163000    | 3.5    |
| Sons and Lovers                    | 162000    | 3.6    |
| The Return of the Native           | 154000    | 3.7    |
| As I Lay Dying                     | 57000     | 3.5    |
# Graph

```sqlseal
TABLE d = table(0)
CHART {
	xAxis: {
		type: 'log',
		logBase: '2'
	},
	yAxis: {
		min: 1
	},
	tooltip: { },
	series: [{
		type: 'scatter',
		symbolSize: 5,
		encode: {
			x: 'wordcount',
			y: 'rating',
			tooltip: 'title'
		}
	}]
}
SELECT * FROM d
```
