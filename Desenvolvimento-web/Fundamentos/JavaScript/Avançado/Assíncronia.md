[[Avançado]]
## Fetch
```jsx
fetch(apiUrl)
  .then(response => {
    // Parseia a resposta como JSON e a retorna
    return response.json();
  })
  .then(data => {
    // Aqui você pode manipular os dados recebidos da API
    console.log('Dados da API:', data);
  })
  .catch(error => {
    // Lidando com erros, se ocorrerem
    console.error('Erro:', error);
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