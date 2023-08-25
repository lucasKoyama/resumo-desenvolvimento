```js
import { legacy_createStore as createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import { composeWithDevTools } from '@redux-devtools/extension';
import rootReducer from './reducers';

const store = createStore(
	rootReducer,
	composeWithDevTools(applyMiddleware(thunk))
);

if (window.Cypress) { // para rodar com os testes do cypress
  window.store = store;
}

export default store;
```
