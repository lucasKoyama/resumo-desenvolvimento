```jsx
import { useContext } from 'react';
import ThemeContext from '../context/ThemeContext';

function Header() {
	// Context sendo usado ao passar como parametro o context para o 
	// hook useContext()
	const theme = useContext(ThemeContext);
	
	return (
		<header>
			<button onClick={() => theme.toggleTheme()}>
					{theme.color === 'dark' ? '☀️' : '🌒'}
			</button>
		</header>
	);
}

export default Header;
```
Este **componente é filho** do [[ThemeProvider.jsx]] sendo assim tem acesso ao seu context ao usar o hook **useContext** guardando o retorno de duas formas:
1. **variável**
```jsx
const theme = useContext(ThemeContext);
```
2. **desestruturação dos dados**
```jsx
const { toggleTheme, theme } = useContext(ThemeContext);
```