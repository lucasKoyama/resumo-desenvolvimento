[[Intermediário]]
## Local Storage

```jsx
// O LocalStorage só guarda strings, e o método stringify() transforma o input em string
localStorage.setItem('storageName', JSON.stringify(not_a_string));

/* Recupera uma informação do localStorage caso ela exista, e a transforma de volta para o tipo original, que pode ser objeto, array, etc, utilizando o parse() */
const storage = localStorage.getItem('storageName');
if (storage) { const storageName = JSON.parse(storage); }
```