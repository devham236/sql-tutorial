## Wildcards

- Um nach bestimmten string characters in einem Eintrag zu suchen bzw. wenn man anch einem bestimmten Wort suchen möchte, kann man das 'LIKE' keyword und % verwenden.

```js
// % = any number of characters
// _ = one character

SELECT *
FROM client
WHERE client_name LIKE '%LLC';
```

- '%LLC' bedeutet das LLC am Ende vom client_name steht, das % beschreibt die beliebig vielen characters vor dem LLC.

```js
SELECT *
FROM branch_supplier
WHERE supplier_name LIKE '% Label%';
```

- Je nachdem wo man das % platziert sagt man aus wo der string 'Label' sich befindet und ob characters noch vorher oder nachher auftreten.

```js
// birth_date structure = '1978-10-01' (YYYY-MM-DD)

SELECT *
FROM employee
WHERE birth_date LIKE '____-10%';
```

- Man kann auch das '\_' verwenden um einen character zu beschreiben, oben im Beispiel suchen wir nach Einträgen die mit 4 undersccores anfangen, worauf eine 10 folgt und dann beliebig viele characters folgen
- Gesucht werden employees die im Oktober geboren wurden.
