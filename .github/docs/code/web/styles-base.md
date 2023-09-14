# `web/styles/base.css`

## Função

Em resumo, este código CSS está estilizando a página da web da seguinte maneira:

- Define um comportamento de rolagem suave.
- Melhora a renderização de fontes em navegadores específicos.
- Configura o estilo para o corpo da página, incluindo cores de fundo, texto, tamanho e disposição.
- Aplica a família de fontes "Roboto" aos elementos `body`, `button` e `input` da página.

## Anotações

1. `* {` - Isso é um seletor universal, que se aplica a todos os elementos HTML na página. A partir deste ponto, todas as regras de estilo dentro deste bloco se aplicarão a todos os elementos.

2. `scroll-behavior: smooth;` - Esta linha define o comportamento de rolagem suave para a página. Quando um link âncora é clicado e leva a uma seção diferente da página, a página rolará suavemente até a nova seção.

3. `-webkit-font-smoothing: antialiased;` - Isso melhora a renderização de fontes no navegador da Web Safari, suavizando as bordas das fontes para torná-las mais nítidas e legíveis.

4. `-moz-osx-font-smoothing: grayscale;` - Isso melhora a renderização de fontes no navegador Mozilla Firefox, tornando as fontes mais nítidas e legíveis.

5. `}` - Fecha o bloco de regras para o seletor universal (*).

6. `body {` - Isso seleciona o elemento `body` da página HTML. As regras dentro deste bloco se aplicam especificamente ao corpo da página.

7. `margin: 0;` - Define a margem externa do corpo como zero, removendo qualquer espaço em branco ao redor do corpo da página.

8. `padding: 0;` - Define o preenchimento interno do corpo como zero, removendo qualquer espaço em branco dentro do corpo da página.

9. `box-sizing: border-box;` - Define o modelo de caixa para "border-box", o que significa que o tamanho total de um elemento inclui a largura e a altura, incluindo as bordas e o preenchimento, mas não a margem.

10. `background-color: #121214;` - Define a cor de fundo do corpo como um tom de cinza escuro (#121214).

11. `color: #fff;` - Define a cor do texto do corpo como branco (#fff).

12. `width: 100%;` - Define a largura do corpo como 100% da largura do viewport.

13. `height: 100vh;` - Define a altura do corpo como 100% da altura do viewport. Isso faz com que o corpo da página ocupe toda a altura da janela do navegador.

14. `display: flex;` - Define a exibição do corpo como "flex", permitindo que os elementos dentro dele se comportem como um contêiner flexível.

15. `flex-direction: column;` - Define a direção do fluxo flexível como uma coluna, o que significa que os elementos dentro do corpo serão empilhados verticalmente.

16. `justify-content: center;` - Centraliza verticalmente os elementos dentro do corpo.

17. `align-items: center;` - Centraliza horizontalmente os elementos dentro do corpo.

18. `}` - Fecha o bloco de regras para o seletor `body`.

19. `body, button, input {` - Isso seleciona os elementos `body`, `button` e `input` da página HTML. As regras dentro deste bloco se aplicam especificamente a esses elementos.

20. `font-family: "Roboto", sans-serif;` - Define a família de fontes para "Roboto" para esses elementos. Se a fonte "Roboto" não estiver disponível, o navegador usará uma fonte sans-serif genérica como alternativa.

21. `}` - Fecha o bloco de regras para os seletores `body`, `button` e `input`.

> Voltar para o [`code-index`](../../code-index.md)
