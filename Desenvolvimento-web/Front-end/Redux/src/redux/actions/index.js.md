```js
/* Importe as ações e crie funções para cada tipo de ação*/
import {
  SUBMIT_USER_LOGIN_DATA,
} from './actionTypes';

export const userLoginData = (userEmail) => ({
  type: SUBMIT_USER_LOGIN_DATA,
  payload: userEmail,
});
