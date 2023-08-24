#globalstate
[[React.js]]

2. Crie o `**Provider**`, exemplo com fetch de preferência dentro da pasta context

```jsx
import React, { useState, useEffect } from 'react';
import PropTypes from 'prop-types';
import ExampleContext from './ExampleContext';

function ExampleProvider({ children }) {
  const [example, setExample] = useState([]);

  const fetchExample = async () => {
    const response = await fetch('url');
    const data = await response.json();
    setExample(data);
  };

  useEffect(() => { fetchExample(); }, []);

  return (
    <ExampleContext.Provider value={ { example } }>
      {children}
    </ExampleContext.Provider>
  );
}

ExampleProvider.propTypes = ({
  children: PropTypes.element,
}).isRequired;

export default ExampleProvider;
```

1. Consuma o `C**ontext**` na onde for necessário

```jsx
import React, { useContext } from 'react';
import ExampleContext from './ExampleContext';

const consumerComponent = () => {
  const { example } = useContext(ExampleContext);

  return (
    <h1>{example}</h1>
  );
};

export default consumerComponent;
```

1. Envolva o `**Provider**` com os componentes filhos que deseja compartilhar os dados, se for na aplicação toda que quer compartilhar coloque no **App**

```jsx
import React from 'react';
import ExampleProvider from './context/ExampleProvider';
import Table from './components/Table';
import './App.css';

function App() {
  return (
    <ExampleProvider>
      <Table />
    </ExampleProvider>
  );
}

export default App;
```