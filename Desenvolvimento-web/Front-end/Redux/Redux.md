#globalstate 
[[Front-end]]
1. **Instalação de dependências**:
- [ ]  **redux**
- [ ]  **redux-thunk**
- [ ]  **extensão auxiliar** por último

```bash
npm i --save redux react-redux redux-thunk @redux-devtools/extension
```

1. Criação  de pastas e arquivos com códigos dentro da pasta `src` de forma organizada hierarquicamente:

<aside>
💡 **O passo descrito está estruturado como se fosse de fato pastas e arquivos, logo ao clicar na seta você verá o que contém dentro das pastas e dos arquivos!**

</aside>

- Pasta **`src`**:
    - Pasta **`redux`**:
        - Pasta **`actions`**
            - Arquivo ******`actionTypes.js`******
                
                ```jsx
                // Centraliza todas as actions em um lugar só para melhor organização
                const EXAMPLE_ACTION_1 = 'EXAMPLE_ACTION_1';
                const EXAMPLE_ACTION_FETCH = 'EXAMPLE_ACTION_FETCH';
                const ACTION_SAVE_DATA_FETCH = 'ACTION_SAVE_DATA_FETCH';
                
                export { EXAMPLE_ACTION_1, EXAMPLE_ACTION_FETCH, ACTION_SAVE_DATA_FETCH };
                ```
                
            - Arquivo **************`**index.js**`**************
                
                ```jsx
                /* Importa as actions e define o type para que o reducer
                saiba o que fazer com o state */
                import {
                  EXAMPLE_ACTION_1,
                  EXAMPLE_ACTION_FETCH,
                  ACTION_SAVE_DATA_FETCH,
                } from "./actionTypes";
                
                const submitExample1 = (data) => ({
                  type: EXAMPLE_ACTION_1, payload: data
                });
                
                const saveDataFetch = (data) => ({
                  type: ACTION_SAVE_DATA_FETCH, payload: data
                })
                
                export const fetchExample = () => async (dispatch) => {
                  try {
                    const response = await fetch('url');
                    const data = await response.json();
                    dispatch(saveDataFetch(data));
                  } catch (error) {
                    console.error(error);
                  }
                };
                
                export {submitExample1 , submitExample2 };
                ```
                
        - Pasta **`reducers`**
            - Arquivo **`exampleReducer.js`**
                
                ```jsx
                const INITIAL_STATE = {
                	data: '',
                  fetch: '',
                };
                
                const ****************exampleReducer****************= (state = INITIAL_STATE, action) => {
                 switch(action.type) {
                   case EXAMPLE_ACTION_1:
                	  return { ...state, data: action.payload }
                   case ACTION_SAVE_DATA_FETCH:
                	  return { ...state, fetch: action.payload }
                   default:
                    return state;
                 }
                }
                
                export default ****************exampleReducer****************;
                ```
                
            - Arquivo **************`**index.js**`**************
                
                ```jsx
                import { combineReducers } from "redux";
                import ****************exampleReducer**************** from "./****************exampleReducer****************";
                
                const rootReducer = combineReducers({
                    example: ****************exampleReducer****************
                });
                
                export default rootReducer;
                ```
                
        - Arquivo **`store.js`**
            
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
            
    - Arquivo **************`**index.js**`**************
        
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
        
