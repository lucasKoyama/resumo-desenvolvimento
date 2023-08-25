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
            - [[index.js]]
        - **reducers**
            - [[user.js]]
            - [[index.js]]
        - [[store.js]]
            
            ```jsx
            // COM O THUNK
            import { legacy_createStore as createStore, applyMiddleware } from 'redux';
            import { composeWithDevTools } from '@redux-devtools/extension';
            import thunk from 'redux-thunk';
            import rootReducer from '../reducers';
            
            const middleware = applyMiddleware(thunk);
            const store = createStore(rootReducer, composeWithDevTools(middleware));
            
            if (window.Cypress) { // para rodar com os testes do cypress
              window.store = store;
            }
            
            export default store;
            ```
            
    - index.js
        
        ```jsx
        import React from 'react';
        import ReactDOM from 'react-dom/client';
        import { Provider } from 'react-redux';
        import { BrowserRouter } from 'react-router-dom';
        import App from './App';
        import store from './redux/store';
        import './index.css';
        
        const root = ReactDOM.createRoot(document.getElementById('root'));
        root.render(
          <BrowserRouter>
            <Provider store={ store }>
              <App />
            </Provider>
          </BrowserRouter>,
        );
        ```
        
