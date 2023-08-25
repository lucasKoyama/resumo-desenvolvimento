```js
/* Esse reducer será responsável por capturar um despacho e então identificar seu tipo performando a ação de salvar o email no estado global da aplicação */
import { SUBMIT_USER_LOGIN_DATA } from '../actions/actionTypes';

const INITIAL_STATE = {
  email: '',
};

const userReducer = (state = INITIAL_STATE, action) => {
  switch (action.type) {
  case SUBMIT_USER_LOGIN_DATA:
    return { ...state, email: action.payload };
  default:
    return state;
  }
};

export default userReducer;
```
