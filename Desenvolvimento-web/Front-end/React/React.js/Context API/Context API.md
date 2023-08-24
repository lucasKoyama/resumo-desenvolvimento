#globalstate
## O que é?
O Context API é uma forma simples de gerenciar o estado global de uma aplicação [[React.js]]
## Passos
1. Crie um [[ThemeContext.jsx|context]] para armazenar globalmente os dados
2. Crie o [[ThemeProvider.jsx|provedor do context]] que irá prover os dados para os componentes filhos (children)
3. Coloque os componentes que deseja ter acesso ao context como sendo componentes filhos do [[ThemeProvider.jsx|provedor do context]]
4. No [[Header.jsx|componente filho]] use o context
## Estrutura das pastas e arquivos
- src
	- components
		- [[Header.jsx]]
	- context
		- [[ThemeContext.jsx]]
		- [[ThemeProvider.jsx]]
	
	- [[App.jsx]]