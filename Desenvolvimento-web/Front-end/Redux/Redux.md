#globalstate 
## O que é Redux?
Uma forma complexa e robusta de gerenciar o estado global de uma aplicação no [[Front-end]]
## Passos
1. **Instale as dependências**:
	- [ ]  **redux**
	- [ ]  **redux-thunk**
	- [ ]  **extensão auxiliar** por último
	```bash
	npm i --save redux react-redux redux-thunk @redux-devtools/extension
	 ```
 2. Crie a pasta **redux**
 3. Crie a pasta **actions** dentro da pasta **redux**
	 1. Crie o arquivo [[actionTypes.js]] que irá conter todos os **tipos de ações** do seu redux
	 2. Crie o arquivo [[Desenvolvimento-web/Front-end/Redux/src/redux/actions/index.js|index.js]] e as **funções** para cada **tipo de ação**
 4. Crie a pasta **reducers** dentro da pasta **redux**
	 1. Crie os arquivos de reducer que irá **capturar os despachos** e verificar de que **tipo** é para então **transformar** aquela informação em algo. Exemplo do [[user.js|user reducer]]
			*reducer em inglês significa reduzir, transformar, simplificar, converter e por aí vai!*
	 2. Crie o arquivo [[Desenvolvimento-web/Front-end/Redux/src/redux/reducers/index.js|index.js]] para compilar todos os reducers na variável **rootReducer**
 5. Crie o arquivo [[store.js]] para criar a **variável de acesso ao estado global do redux e suas ferramentas de desenvolvimento**
 6. Modifique o [[Desenvolvimento-web/Front-end/Redux/src/index.js|index.js]] para **prover** a aplicação com a **store contendo o estado global**
 7. **Conecte** todos os componentes que de alguma forma for interagir com o redux seja através dos **despachos** ou **lendo os estados global**.
	 1. Exemplo do [[Login.jsx]] se **conectando** ao redux para ter acesso a **função dispatch** que será usada para **despachar a função que armazena os dados de login no estado global**.
	 2. Exemplo do [[Desenvolvimento-web/Front-end/Redux/src/components/Header.jsx|Header.jsx]] se **conectando** para **mapear o estado** do email **para as props do componente**.
## Estrutura das pastas e arquivos
-  **src**
    - **components**
	    - [[Desenvolvimento-web/Front-end/Redux/src/components/Header.jsx|Header.jsx]]
    - **pages**
	    - [[Login.jsx]]
    - **redux**:
        - **actions**
            -  [[actionTypes.js]]
            - [[Desenvolvimento-web/Front-end/Redux/src/redux/actions/index.js|index.js]]
        - **reducers**
            - [[user.js]]
            - [[Desenvolvimento-web/Front-end/Redux/src/redux/reducers/index.js|index.js]]
        - [[store.js]]
    - [[Desenvolvimento-web/Front-end/Redux/src/index.js|index.js]]