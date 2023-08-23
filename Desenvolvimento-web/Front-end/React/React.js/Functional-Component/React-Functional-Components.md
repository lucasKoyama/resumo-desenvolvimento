[[React.js]]

## State
## Life Cycle - Use Effect

```jsx
// Executa a callback sempre que o componente é renderizado (atualização de estado)
useEffect(() => {}); // componentDidUpdate()

// Executa callback apenas na primeira renderização do componente. 
useEffect(() => {}, []); // componentDidMount()

// Executa callback sempre que qualquer um dos itens do array sofrer alteração. 
useEffect(() => {}, [foo, bar, ...baz]);

// Executa a callback do retorno no momento da desmontagem do componente
useEffect(() => { return () => {}; }, []); // componentWillUnmount()
```
