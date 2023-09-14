# `web/styles/form.css`

## Função

Definir aparência de um formulário web

## Anotações

```css
#form {
  margin-top: 64px;
  display: flex;
  gap: 12px;
}
```

Nesta seção, o código define estilos para um elemento com a ID "form".

- `margin-top: 64px;`: Define uma margem superior de 64 pixels para o elemento com ID "form". Isso cria um espaço vazio acima do formulário.
- `display: flex;`: Define a exibição flexível para o elemento com ID "form", o que geralmente é usado para criar layouts responsivos.
- `gap: 12px;`: Define um espaçamento de 12 pixels entre os elementos filhos do elemento com ID "form". Isso cria espaço entre os elementos do formulário.

```css
#form > input {
  height: 48px;
  width: 450px;
  border: none;
  color: #fff;
  background-color: #202024;
  border-radius: 5px;
  padding: 0 12px;
  font-size: 16px;
}
```

Esta parte do código define estilos para os elementos `input` que são descendentes diretos do elemento com ID "form".

- `height: 48px;`: Define a altura dos campos de entrada como 48 pixels.
- `width: 450px;`: Define a largura dos campos de entrada como 450 pixels.
- `border: none;`: Remove a borda dos campos de entrada.
- `color: #fff;`: Define a cor do texto dentro dos campos de entrada como branco (#fff).
- `background-color: #202024;`: Define a cor de fundo dos campos de entrada como uma tonalidade de cinza (#202024).
- `border-radius: 5px;`: Adiciona um raio de borda de 5 pixels para arredondar as bordas dos campos de entrada.
- `padding: 0 12px;`: Define um preenchimento interno de 12 pixels à esquerda e à direita dos campos de entrada.
- `font-size: 16px;`: Define o tamanho da fonte dentro dos campos de entrada como 16 pixels.

```css
#form > input:focus {
  outline: 2px solid #8257e5;
}
```

Esta parte do código define os estilos que serão aplicados aos campos de entrada quando eles estiverem em foco (quando o usuário clicar neles).

- `outline: 2px solid #8257e5;`: Define uma borda sólida de 2 pixels de espessura com a cor #8257e5 ao redor do campo de entrada em foco. Isso cria um destaque visual quando o usuário interage com o campo de entrada.

```css
#form > input:valid {
  background-color: #202024;
}
```

Esta parte do código define os estilos que serão aplicados aos campos de entrada quando eles estiverem em um estado "válido". O estado "válido" geralmente é aplicado a campos que passaram na validação de dados.

- `background-color: #202024;`: Define a cor de fundo dos campos de entrada no estado "válido" como a mesma cor de fundo definida anteriormente (#202024). Isso pode ser usado para redefinir a cor de fundo após um erro de validação.

```css
#form > button {
  height: 48px;
  width: 48px;
  border: none;
  border-radius: 5px;
  background-color: #8257e5;
  cursor: pointer;
  transition: background-color 0.2s;
}
```

Esta parte do código define estilos para o botão dentro do formulário.

- `height: 48px;`: Define a altura do botão como 48 pixels.
- `width: 48px;`: Define a largura do botão como 48 pixels.
- `border: none;`: Remove a borda do botão.
- `border-radius: 5px;`: Adiciona um raio de borda de 5 pixels para arredondar as bordas do botão.
- `background-color: #8257e5;`: Define a cor de fundo do botão como uma tonalidade de roxo (#8257e5).
- `cursor: pointer;`: Define o cursor do mouse como uma mão quando passa sobre o botão, indicando que é interativo.
- `transition: background-color 0.2s;`: Aplica uma transição suave de 0.2 segundos à cor de fundo do botão quando o mouse passa sobre ele.

```css
#form > button:hover {
  background-color: #633bbc;
}
```

Esta parte do código define os estilos que serão aplicados ao botão quando o mouse estiver sobre ele (estado de "hover").

- `background-color: #633bbc;`: Altera a cor de fundo do botão para uma tonalidade diferente de roxo (#633bbc) quando o mouse está sobre ele. Isso fornece um feedback visual ao usuário quando o botão pode ser clicado.

```css
#form > button i {
  font-size: 24px;
  color: #fff;
}
```

Esta parte do código parece estar relacionada a ícones dentro do botão (usando uma tag `<i>` ou similar dentro do botão).

- `font-size: 24px;`: Define o tamanho da fonte dos ícones como 24 pixels.
- `color: #fff;`: Define a cor dos ícones como branco (#fff). Isso garante que os ícones dentro do botão sejam exibidos em branco.

> Voltar para o [`code-index`](../../code-index.md)
