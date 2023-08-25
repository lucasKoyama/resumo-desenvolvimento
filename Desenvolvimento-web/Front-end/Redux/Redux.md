#globalstate 
[[Front-end]]
## O que é Redux?
O Context API é uma forma simples de gerenciar o estado global de uma aplicação [React.js](app://obsidian.md/React.js)
## Passos
1. **Instalação de dependências**:
	- [ ]  **redux**
	- [ ]  **redux-thunk**
	- [ ]  **extensão auxiliar** por último
	```bash
	npm i --save redux react-redux redux-thunk @redux-devtools/extension
	```
## Estrutura das pastas e arquivos
-  **src**
    - **redux**:
        - **actions**
            -  [[actionTypes.js]]
            - [[Desenvolvimento-web/Front-end/Redux/src/redux/actions/index.js|index.js]]
        - **reducers**
            - [[user.js]]
            - [[Desenvolvimento-web/Front-end/Redux/src/redux/reducers/index.js|index.js]]
        - [[store.js]]
    - [[Desenvolvimento-web/Front-end/Redux/src/index.js|index.js]]