```js
// Esse reducer será responsável por tratar o todas as informações relacionadas as despesas
// Esse reducer será responsável por tratar as informações da pessoa usuária
import {
  GET_CURRENCIES,
  ADD_EXPENSE,
  REMOVE_EXPENSE,
  EDIT_EXPENSE_START,
  EDIT_EXPENSE_DONE,
} from '../actions/actionTypes';

const INITIAL_STATE = {
  currencies: [],
  expenses: [],
  editor: false,
  idToEdit: 0,
};

const walletReducer = (state = INITIAL_STATE, action) => {
  switch (action.type) {
  case GET_CURRENCIES:
    return { ...state, currencies: action.payload };
  case ADD_EXPENSE:
    return {
      ...state,
      expenses: [...state.expenses, { id: state.expenses.length, ...action.payload }],
    };
  case REMOVE_EXPENSE:
    return { ...state, expenses: [...action.payload] };
  case EDIT_EXPENSE_START:
    return { ...state, editor: true, idToEdit: action.payload };
  case EDIT_EXPENSE_DONE:
    return {
      ...state,
      expenses: [...action.payload],
      editor: false,
      idToEdit: 0,
    };
  default:
    return state;
  }
};

export default walletReducer;
```
