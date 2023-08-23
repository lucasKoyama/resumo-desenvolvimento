[[Javascript]]
## Fetch

```jsx
fetch("url")
  .then(response => response.json())
  .then(data => {
  // Aqui vai alguma lógica que usa a resposta da API, a "data"
  console.log(data)
});
```

## Async & Await

```jsx
try {
  const response = await fetch(`url`);
  const data = await response.json();
	// Alguma lógica que use a resposta da API
  console.log(data);
} catch(error) {
  // Caso acontece alguma erro no escopo do try, entra no escopo do catch
  console.log(error)
}
```