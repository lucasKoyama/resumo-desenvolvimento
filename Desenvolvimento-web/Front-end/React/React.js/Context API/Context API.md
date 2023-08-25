#globalstate
## O que é Context API?
O Context API é uma forma simples de gerenciar o estado global de uma aplicação [[React.js]]
## Passos
1. Crie a pasta **context**
2. Crie um [[ThemeContext.jsx|context]] para armazenar globalmente os dados dentro da pasta **context**
3. Crie o [[ThemeProvider.jsx|provedor do context]] que irá prover os dados para os componentes filhos (children) dentro da pasta **context**
4. Coloque os componentes que deseja ter acesso ao context como sendo componentes [[Desenvolvimento-web/Front-end/React/React.js/Context API/src/components/Header.jsx|filhos]] do [[ThemeProvider.jsx|provedor do context]], normalmente o componente filho é o próprio **App.jsx**
5. No [[Desenvolvimento-web/Front-end/React/React.js/Context API/src/components/Header.jsx|componente filho]] use o context
## Estrutura das pastas e arquivos
- **src**
	- **components**
		- [[Desenvolvimento-web/Front-end/React/React.js/Context API/src/components/Header.jsx]]
	- **context**
		- [[ThemeContext.jsx]]
		- [[ThemeProvider.jsx]]
	
	- [[App.jsx]]