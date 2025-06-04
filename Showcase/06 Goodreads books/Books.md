---
author: Kurt Vonnegut
---
```sqlseal
TABLE books = file(books.csv)

HTML
SELECT
	a('https://openlibrary.org/isbn/' || CAST(isbn13 as int), title) as title,
	authors,
	img('https://covers.openlibrary.org/b/isbn/' || CAST(isbn13 as INT) || '-L.jpg') as cover FROM books
WHERE authors
	LIKE '%' || @author || '%'
	AND NOT isbn LIKE '%X' 
LIMIT 10
```
