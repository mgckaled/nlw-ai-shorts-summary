# Notas importantes

## Conceitos

### O que é Cors?

Cross-Origin Resource Sharing (CORS) é uma política de segurança implementada pelos navegadores da web para controlar as solicitações feitas a recursos em um domínio diferente do que o da página que está fazendo a solicitação. Isso ajuda a prevenir ataques de segurança, como solicitações entre sites (cross-site request forgery) e vazamento de informações confidenciais.

Quando você faz uma solicitação HTTP de um site para outro (por exemplo, de um site web A para um site web B), o navegador normalmente bloqueia essa solicitação devido à política de mesma origem (same-origin policy). O CORS é uma maneira de relaxar essa política e permitir que servidores indiquem explicitamente quais origens podem acessar seus recursos.

Exemplo de código Node.js usando o módulo `http` que demonstra como configurar o CORS em um servidor Node.js:

```javascript
import http from 'http';

const server = http.createServer((req, res) => {
  // Configura os cabeçalhos CORS para permitir qualquer origem (não seguro em produção)
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, PUT, DELETE');
  res.setHeader('Access-Control-Allow-Headers', 'Content-Type, Authorization');

  // Lida com diferentes tipos de solicitações
  if (req.method === 'OPTIONS') {
    // Responde a solicitações OPTIONS (pré-voo) sem processamento adicional
    res.writeHead(204);
    res.end();
  } else if (req.method === 'GET') {
    // Lida com solicitações GET
    // Aqui você pode responder com os dados solicitados
    res.writeHead(200, { 'Content-Type': 'application/json' });
    const responseData = { message: 'Exemplo de resposta CORS habilitada.' };
    res.end(JSON.stringify(responseData));
  } else {
    // Lida com outros tipos de solicitações (POST, PUT, DELETE, etc.)
    res.writeHead(405); // Método não permitido
    res.end();
  }
});

const PORT = process.env.PORT || 3000;

server.listen(PORT, () => {
  console.log(`Servidor Node.js em execução na porta ${PORT}`);
});
```

Neste exemplo, configuramos os cabeçalhos CORS para permitir qualquer origem usando `res.setHeader('Access-Control-Allow-Origin', '*')`. No entanto, em um ambiente de produção, você deve especificar origens permitidas de forma mais restrita para aumentar a segurança.

Além disso, respondemos a solicitações OPTIONS (pré-voo) sem processamento adicional, pois o navegador pode enviar uma solicitação OPTIONS antes de uma solicitação real para verificar se a solicitação é permitida. As solicitações GET são manipuladas retornando uma resposta JSON simples.

Lembre-se de que a configuração de CORS depende das necessidades específicas do seu aplicativo e dos riscos de segurança associados. Em produção, você deve configurar o CORS de forma mais restritiva, permitindo apenas as origens necessárias para acessar seus recursos.

> Voltar para o [`code-index`](./code-index.md)
