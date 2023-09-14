# `web/styles/app.css`

## Função

Estilização

## Anotações

```css
#app {
  display: flex;
  flex-direction: column;
  align-items: center;
}
```

1. `#app`: Isso se refere a um elemento HTML que possui o atributo `id` definido como "app". O seletor `#` é usado para selecionar elementos com um ID específico.
2. `display: flex;`: Isso define o valor da propriedade `display` como "flex". Isso indica que o elemento com ID "app" será exibido como um contêiner flexível.
3. `flex-direction: column;`: Isso define a direção principal do fluxo de conteúdo dentro do elemento "app" como uma coluna. Os elementos filhos serão empilhados verticalmente.
4. `align-items: center;`: Isso alinha os itens dentro do elemento "app" horizontalmente, centralizando-os no eixo transversal.

```css
#app > h1 {
  color: #996dff;
  margin-top: -5px;
}
```

1. `#app > h1`: Isso seleciona um elemento `h1` que é filho direto do elemento com ID "app".
2. `color: #996dff;`: Define a cor do texto do elemento `h1` como um tom de roxo (#996dff).
3. `margin-top: -5px;`: Define uma margem negativa no topo do elemento `h1`, deslocando-o para cima em 5 pixels.

```css
#app > h2 {
  align-self: flex-start;
  margin-top: 64px;
}
```

1. `#app > h2`: Isso seleciona um elemento `h2` que é filho direto do elemento com ID "app".
2. `align-self: flex-start;`: Define a propriedade `align-self` para "flex-start", o que significa que o elemento `h2` alinhará a si mesmo à extremidade inicial do eixo principal do elemento "app".
3. `margin-top: 64px;`: Define uma margem superior de 64 pixels para o elemento `h2`, criando um espaço em branco entre ele e os elementos acima.

```css
#app > p {
  align-self: flex-start;
  text-align: justify;
  width: 512px;
  margin-top: -5px;
}
```

1. `#app > p`: Isso seleciona um elemento `p` que é filho direto do elemento com ID "app".
2. `align-self: flex-start;`: Assim como no elemento `h2`, define a propriedade `align-self` como "flex-start" para o elemento `p`.
3. `text-align: justify;`: Define o alinhamento do texto no elemento `p` como "justify", o que cria espaços adicionais entre as palavras para alinhar o texto às margens esquerda e direita.
4. `width: 512px;`: Define a largura do elemento `p` como 512 pixels.
5. `margin-top: -5px;`: Define uma margem superior negativa de 5 pixels para o elemento `p`, deslocando-o para cima em relação à sua posição normal.

```css
#app .placeholder {
  color: #7c7c8a;
  user-select: none;
}
```

1. `#app .placeholder`: Isso seleciona elementos com a classe "placeholder" que estão dentro do elemento com ID "app".
2. `color: #7c7c8a;`: Define a cor do texto desses elementos como um tom de cinza (#7c7c8a).
3. `user-select: none;`: Isso impede que o texto dentro dos elementos com a classe "placeholder" seja selecionado pelo usuário, tornando-o não interativo.

> Voltar para o [`code-index`](../../code-index.md)
