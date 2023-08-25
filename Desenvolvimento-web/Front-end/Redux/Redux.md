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
 2. Criar a pasta **redux**
 3. Criar a pasta **actions** dentro de redux
	 1. Criar o arquivo [[actionTypes.js]] que irá conter todos os tipos de ações do seu redux
	 2. Criar o arquivo [[Desenvolvimento-web/Front-end/Redux/src/redux/actions/index.js|index.js]] e as **funções** para cada tipo de ação
 4. Criar a pasta **reducers** dentro de redux
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