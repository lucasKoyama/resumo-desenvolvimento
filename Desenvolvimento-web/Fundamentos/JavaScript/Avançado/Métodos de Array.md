[[Avançado]]
## Includes - verifica se existe algum item no array

```jsx
array.includes(item); // Verifica se no array contém algum item e retorna um boolean.
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

---

## Local Storage

```jsx
// O LocalStorage só guarda strings, e o método stringify() transforma em string o input
localStorage.setItem('storageName', JSON.stringify(not_a_string));

/* Recupera uma informação do localStorage caso ela exista e a transforma de volta para o tipo original, que pode ser objeto, array, etc, utilizando o parse() */
const storage = localStorage.getItem('storageName');
if (storage) { const storageName = JSON.parse(storage); }
```