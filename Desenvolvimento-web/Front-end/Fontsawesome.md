[[Front-end]]

1. Coloque as dependências no package.json e as instale com o `npm i`
```jsx
// package.json
"dependencies": {
  ...
  "@fortawesome/fontawesome-free": "^6.4.0",
  "@fortawesome/fontawesome-svg-core": "^6.4.0",
  "@fortawesome/free-solid-svg-icons": "^6.4.0",
  "@fortawesome/react-fontawesome": "^0.2.0"
  ...
}
```

2. Importe no seu componente (de preferência no App.jsx)
```bash
import '@fortawesome/fontawesome-free/css/all.css';
```

3. Agora basta usar normalmente as tags `<i>` do fontsawesome!