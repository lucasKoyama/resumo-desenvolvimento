[[Avançado]]
## Includes - verifica se existe um item específico no array
```jsx
// Verifica se no array contém algum item e retorna um boolean.
const arr = ['HTML', 'CSS', 'Javascript'];
arr.includes('Javascript'); // true, Javascript está incluso na variável arr
```
---
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
---
## Higher Order Functions - HOFs

### forEach
**Para cada item do array executa uma callback** realizando algo e retorna **undefined**
```js
array.forEach((item) => console.log(item));
```
### map
Para cada item do array executa uma callback realizando algo e retorna um novo array
```js
const arr = [1, 2, 3]; 
const novoArr = arr.map((item) => item + 1); // novoArr = [2, 3, 4]
```
### reduce
- **acumulador / acc**: Variável que irá guardar informações entre todas as iterações.
- **itemAtual / curr**: a cada iteração o itemAtual passa a ser um item do array equivalente ao seu indice
- **valorInicial**: é o valor que o acumulador irá começar, serve para definir se o acumulador será um número, arrray, objeto, etc

A cada iteração a callback do reduce é executada realizando alguma operação envolvendo o item atual da iteração e o acumulador.
```jsx
array.reduce((acumulador, itemAtual) => acumulador + itemAtual, valorInicial);
```
### find
**Percorre cada item do array procurando por algum que satisfaça a condição passada a callback e o retorna quando encontrado**, caso não encontre nada retorna **undefined**
```js
const arr = [
	{ skill: 'HTML', subTopics: ['Semantico', 'Forms'] },
	{ skill: 'CSS', subTopics: ['Flexbox', 'Responsividade'] },
	{ skill: 'Javascript' subTopics: ['Arrays', 'Hofs'] }
];
arr.find((item) => item.skill === 'Javascript');
```
### filter
**Filtra** o array **retornando um array somente com os itens que satisfaça a condição da callback**
```js
const cardapio = ['']
```
### sort