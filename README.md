# Projeto Node.js - servidor web que contém várias rotas.

## Configurações

1. **Certifique-se de ter o Node.js instalado no seu sistema.**

   Se você ainda não tem o Node.js instalado, você pode baixá-lo [aqui](https://nodejs.org/). Escolha a versão recomendada para a sua plataforma e siga as instruções de instalação.

2. Instale o pacote Express usando o npm:

    ```bash
    npm install express
    ```

## Iniciando a criação do projeto.

1. Crie um arquivo chamado `server.js` e adicione o seguinte código:

    ```javascript
    const express = require('express');
    const app = express();
    const port = 3000;
    
    // Rota estática
    app.get('/static', (req, res) => {
      res.send('Esta é uma rota estática. A resposta é a mesma para todas as requisições.');
    });
    
    // Rota dinâmica com placeholder
    app.get('/dynamic/:id', (req, res) => {
      const userId = req.params.id;
      res.send(`Esta é uma rota dinâmica com placeholder. O valor do placeholder é: ${userId}`);
    });
    
    // Rota dinâmica com query string
    app.get('/query', (req, res) => {
      const name = req.query.name || 'Visitante';
      res.send(`Esta é uma rota dinâmica com query string. O parâmetro 'name' na query string é: ${name}`);
    });
    
    // Inicia o servidor
    app.listen(port, () => {
      console.log(`Servidor web rodando em http://localhost:${port}`);
    });
    ```

2. No terminal, execute o seguinte comando para iniciar o servidor:

    ```bash
    node server.js
    ```

3. Prontinho, agora você pode acessar as diferentes rotas:

   - Rota estática: [http://localhost:3000/static](http://localhost:3000/static)
   - Rota dinâmica com placeholder: [http://localhost:3000/dynamic/123](http://localhost:3000/dynamic/123) (substitua 123 por qualquer valor)
   - Rota dinâmica com query string: [http://localhost:3000/query?name=SeuNome](http://localhost:3000/query?name=SeuNome) (substitua "SeuNome" por qualquer valor)
