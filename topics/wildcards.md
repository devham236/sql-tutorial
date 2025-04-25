## Wildcards

- Um nach bestimmten string characters in einem Eintrag zu suchen bzw. wenn man anch einem bestimmten Wort suchen möchte, kann man das 'LIKE' keyword und % verwenden.

```js
-- % = any number of characters
-- _ = one character

SELECT *
FROM client
WHERE client_name LIKE '%LLC';
```

- '%LLC' bedeutet das LLC am Ende vom client_name steht, das % beschreibt die beliebig vielen characters vor dem LLC.
