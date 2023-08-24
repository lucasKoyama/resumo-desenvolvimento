[[React.js]]
## Hooks
São funções **enganchadas** em um **componente funcional**, para que crie uma função hook ela deve atender aos requisitos:
- **Nomenclatura:** começar com **"use"**;
- **Não pode ser chamado dentro de um:** **if**, **loop**, **função aninhada**;
- **Onde podem ser chamado:** **componentes funcionais**, **dentro de outros hooks**.
## State - useState
```jsx
// "example" é a variável, "setExample" é uma função para atualizar o valor da variável, ambos são providos pelo hook useState
const [example, setExample] = useState('String inicial do state example');
```
## Life Cycle - useEffect
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
## Timer como exemplo de um componente funcional react


