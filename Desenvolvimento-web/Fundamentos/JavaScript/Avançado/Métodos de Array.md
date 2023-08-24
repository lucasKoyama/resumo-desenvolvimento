[[Avançado]]
## Includes - verifica se existe algum item no array
```jsx
// Verifica se no array contém algum item e retorna um boolean.
array.includes(item);
```
## Formas de remover item do array
```jsx
// Retorna o indice que o elemento foi encontrado no array, útil para usar com splice
array.indexOf(elemento);

// Remove uma quantia de items do array no index especificado e retorna elemento deletado
array.splice(index, quantidade);

// Remove o último elemento do array e o retorna
array.pop();

// Remove o primeiro elemento do array e o retorna
array.shift();
```
## Higher Order Functions - HOFs
### Reduce
```jsx
/* A variável acumulador é criada para guardar informações de cada iteração que vem da  variável iteraçãoAtual, e a variável valorInicial é criada para definir o valor inicial do acumulador. */
// acc=valorInicial => acc + iteração1 => acc + iteração2 => ... => acc + iteraçãoFinal
array.reduce((acumulador, iteraçãoAtual) => acumulador + iteraçãoAtual, valorInicial);
```