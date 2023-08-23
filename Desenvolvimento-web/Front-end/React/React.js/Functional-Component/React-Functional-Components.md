[[React.js]]

## Hooks
## State - Use State
```jsx
// "example" é a variável, "setExample" é uma função para atualizar o valor da variável, ambos são providos pelo hook useState
const [example, setExample] = useState('String inicial do state example');
```

## Life Cycle - Use Effect
```jsx
// Executa a callback sempre que o componente é renderizado
// (atualização de estado causa renderização).
// Equivalente ao componentDidUpdate() do react class
useEffect(() => {});

// Executa callback apenas na primeira renderização do componente.
// Equivalente ao componentDidMount() do react class
useEffect(() => {}, []); 

// Executa callback sempre que qualquer um dos itens do array sofrer alteração.
useEffect(() => {}, [foo, bar, ...baz]);

// Executa a callback do retorno no momento da desmontagem do componente
// Equivalente ao componentWillUnmount() do react class
useEffect(() => {
  return () => {};
}, []); 
```
