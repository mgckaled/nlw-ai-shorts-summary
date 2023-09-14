# `server/download.js`

## Função

Em resumo, este código é uma função assíncrona que permite baixar o áudio de um vídeo do YouTube, com algumas verificações de duração e manipulação de erros, e salva o áudio em um arquivo local.

## Anotações

```javascript
import ytdl from "ytdl-core"
import fs from "node:fs"
```

Nestas linhas, o código importa duas bibliotecas: `ytdl-core` e `fs`. A primeira, `ytdl-core`, é uma biblioteca para baixar vídeos do YouTube. A segunda, `fs`, é uma biblioteca nativa do Node.js para manipulação de arquivos.

```javascript
export const download = (videoId) =>
  new Promise((resolve, reject) => {
```

Esta linha define uma função chamada `download` que recebe um parâmetro `videoId`. A função retorna uma Promise, o que significa que ela é assíncrona e pode ser usada com `await` para esperar que o download seja concluído.

```javascript
    const videoURL = "https://www.youtube.com/shorts/" + videoId
    console.log("Realizando o download do vídeo:", videoId)
```

Aqui, o código cria uma URL completa para o vídeo do YouTube usando o `videoId` fornecido e imprime uma mensagem no console informando que o download está sendo iniciado.

```javascript
    ytdl(videoURL, { quality: "lowestaudio", filter: "audioonly" })
```

Nesta linha, o código usa a função `ytdl` do `ytdl-core` para começar o processo de download. Ele passa a URL do vídeo e algumas opções, especificando que a qualidade deve ser a mais baixa ("lowestaudio") e que apenas o áudio deve ser baixado ("audioonly").

```javascript
      .on("info", (info) => {
        const seconds = info.formats[0].approxDurationMs / 1000

        if (seconds > 60) {
          throw new Error("A duração desse vídeo é maior do que 60 segundos.")
        }
      })
```

Esta parte do código adiciona um ouvinte de evento para o evento "info" que é disparado quando as informações sobre o vídeo estão disponíveis. Ele verifica a duração aproximada do vídeo e, se for maior que 60 segundos, lança um erro, indicando que o vídeo é muito longo.

```javascript
      .on("end", () => {
        console.log("Download do vídeo finalizado.")
        resolve()
      })
```

Aqui, um ouvinte de evento é adicionado para o evento "end", que é disparado quando o download é concluído com sucesso. Ele imprime uma mensagem no console indicando que o download foi finalizado e resolve a Promise, indicando que o download foi bem-sucedido.

```javascript
      .on("error", (error) => {
        console.log(
          "Não foi possível fazer o download do vídeo. Detalhes do erro:",
          error
        )
        reject(error)
      })
```

Esta parte adiciona um ouvinte de evento para o evento "error", que é disparado se ocorrer um erro durante o download. Ele imprime uma mensagem de erro no console, juntamente com os detalhes do erro, e rejeita a Promise, indicando que o download falhou.

```javascript
      .pipe(fs.createWriteStream("./tmp/audio.mp4"))
  })
```

Finalmente, o código utiliza o método `pipe` para direcionar o fluxo de dados do download diretamente para um arquivo local chamado "audio.mp4" no diretório "./tmp". Isso efetivamente salva o áudio do vídeo em um arquivo local.

> Voltar para o [`code-index`](../../code-index.md)
