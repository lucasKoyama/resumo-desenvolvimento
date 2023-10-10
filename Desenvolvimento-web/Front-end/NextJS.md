## O que é NextJS?
Framework [[React.js]] que possibilita:
- Maior velocidade do site devido ao seu sistema de navegação e code splitting (separar e buildar somente o que é necessário por página, aumentando a diminuindo o loading)
- Melhor SEO
- Extrema facilidade de começar um projeto estruturado e configurado para React
## Passos
1. Tenha o node.js e o npm instalados
2. Abra o terminal
3. Crie o projeto `npx create-next-app nome-do-seu-projeto`

## Deploy estático
1. Crie o arquivo `next.config.js` com o seguinte conteúdo:
	```js
	/** @type {import('next').NextConfig} */
	const nextConfig = {
	  output: 'export',
	}
	
	module.exports = nextConfig
	```
2. Rode o comando `npm run build`
3. De deploy do conteúdo da pasta `out` gerada
4. Para pre visualizar o build gerado de o comando `npx serve@latest out`