# `server/convert.js`

## Função

Realizar a conversão de um arquivo de vídeo MP4 em um arquivo de áudio WAV usando a biblioteca `ffmpeg` e outras bibliotecas relacionadas ao Node.js. Ele configura as opções de conversão, decodifica o arquivo de saída e retorna os dados de áudio como um array de números de ponto flutuante. Também trata erros e remove o arquivo de saída após a conversão bem-sucedida.

## Anotações

1 - Importação de módulos:

  ```javascript
  import fs from "node:fs"
  import wav from "node-wav"
  import ffmpeg from "fluent-ffmpeg"
  import ffmpegStatic from "ffmpeg-static"
  ```

- `fs`: É o módulo File System do Node.js, que é usado para interagir com o sistema de arquivos.
- `wav`: É uma biblioteca para lidar com arquivos de áudio WAV.
- `ffmpeg`: É uma biblioteca para trabalhar com o FFmpeg, uma ferramenta de linha de comando usada para processar áudio e vídeo.
- `ffmpegStatic`: Este módulo é usado para fornecer o caminho para a versão estática do FFmpeg incluída no projeto.

2 - Declaração de constantes:

```javascript
const filePath = "./tmp/audio.mp4"
const outputPath = filePath.replace(".mp4", ".wav")
```

- `filePath`: Define o caminho do arquivo de vídeo de entrada no formato MP4.
- `outputPath`: Define o caminho de saída para o arquivo de áudio WAV resultante, que terá o mesmo nome do arquivo de entrada, mas com a extensão alterada para ".wav".

3 - Exportação da função `convert`:

```javascript
export const convert = () =>
  new Promise((resolve, reject) => {
```

- exportando uma função chamada `convert`, que é uma função assíncrona retornando uma Promessa.

4 - Início da conversão de vídeo para áudio:

```javascript
    console.log("Convertendo o vídeo...")

    ffmpeg.setFfmpegPath(ffmpegStatic)
```

- `ffmpeg.setFfmpegPath(ffmpegStatic)`: Configura o caminho para o executável FFmpeg usando a versão estática do FFmpeg fornecida pelo `ffmpegStatic`.

5 - Chaining de métodos do objeto `ffmpeg()`:

```javascript
    ffmpeg()
      .input(filePath)
      .audioFrequency(16000)
      .audioChannels(1)
      .format("wav")
```

- `ffmpeg()`: Cria uma instância do objeto `ffmpeg`.
- `.input(filePath)`: Define o arquivo de entrada para a conversão, que é o arquivo de vídeo especificado em `filePath`.
- `.audioFrequency(16000)`: Define a frequência de áudio desejada para o arquivo de saída como 16.000 Hz (16 kHz).
- `.audioChannels(1)`: Define o número de canais de áudio como 1 (mono).
- `.format("wav")`: Define o formato de saída como WAV.

6 - Manipulação de eventos:

```javascript
      .on("end", () => {
```

- `.on("end", () => { ... })`: Define um manipulador de eventos para quando a conversão for concluída com sucesso.

7 - Leitura e decodificação do arquivo de áudio:

```javascript
        const file = fs.readFileSync(outputPath)
        const fileDecoded = wav.decode(file)
```

- `fs.readFileSync(outputPath)`: Lê o arquivo de áudio WAV recém-criado.
- `wav.decode(file)`: Decodifica o arquivo de áudio WAV em uma estrutura de dados utilizável.

8 - Extração dos dados de áudio:

```javascript
        const audioData = fileDecoded.channelData[0]
        const floatArray = new Float32Array(audioData)
```

- `fileDecoded.channelData[0]`: Obtém os dados de áudio do primeiro canal (mono) do arquivo.
- `new Float32Array(audioData)`: Converte os dados de áudio em um array de números de ponto flutuante (floats).

9 - Conclusão bem-sucedida da conversão:

```javascript
        console.log("Vídeo convertido com sucesso!")

        resolve(floatArray)
        fs.unlinkSync(outputPath)
      })
```

- `console.log("Vídeo convertido com sucesso!")`: Exibe uma mensagem de sucesso.
- `resolve(floatArray)`: Resolve a Promessa com o array de dados de áudio resultante.
- `fs.unlinkSync(outputPath)`: Remove o arquivo de áudio WAV após a conclusão da conversão.

10 - Tratamento de erro:

```javascript
      .on("error", (error) => {
        console.log("Erro ao converter o vídeo", error)
        reject(error)
      })
```

- `.on("error", (error) => { ... })`: Define um manipulador de eventos para lidar com erros durante a conversão.
- `reject(error)`: Rejeita a Promessa com o erro ocorrido.

11 - Salvar o arquivo de áudio convertido:

```javascript
      .save(outputPath)
  })
```

- `.save(outputPath)`: Salva o arquivo de áudio WAV convertido no caminho especificado em `outputPath`.

> Voltar para o [`code-index`](../../code-index.md)
