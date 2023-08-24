[[React.js]]
## Hooks
São funções **enganchadas** em um **componente funcional**. Para criar uma função hook ela deve atender aos requisitos:
- **Nomenclatura:** começar com **"use"**;
- **Não pode ser chamado dentro de um:** **if**, **loop**, **função aninhada**;
- **Somente podem ser chamadas dentro de:** **componentes funcionais**, **outros hooks**.
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
```jsx
// Timer.jsx
import { useState, useEffect } from 'react';
import PropTypes from 'prop-types';

const Timer = ({ initialTime }) => {
	// variável "time" iniciada com o valor da prop "initialTime"
	// função "setTime" atualiza o valor da variável
	const [time, setTime] = useState(initialTime);

	// useEffect com a variável "time" dentro do array, toda vez que a variável
	// atualiza a callback será executada
	useEffect(() => {
		if (time > 0) {
			const timer = setInterval(() => {
				setTime(prevTime => prevTime - 1);
			}, 1000);
			return () => clearInterval(timer);
		}
	}, [time]);
	
	return (
		<div>
			<h1>Countdown Timer</h1>
			<div>Time remaining: {time} seconds</div>
		</div>
	);
};

// definindo que o tipo da prop "initialTime" será um número
Timer.propTypes = ({
	initialTime: PropTypes.number,
}).isRequired;

export default Timer;
```
Usando o Timer no App
```jsx
//App.jsx
import Timer from './Timer'

function App() {
	return (
		<>
			<Timer initialTime={60} />
		</>
	)
}

export default App
```

