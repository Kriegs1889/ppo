# 2024-IA22-2TRI

# Iniciando um projeto Node.js com TypeScript
- abra o github e crie um repositório,para criar um repositório, va na barra da esquerda, clique no botao "new", vá em "repository name" e de um nome a seu seu repositório, depois,  vá para a opção "add a README file" e a habilite. Após isso, apenas clique na opção "create repository" e parabens, voce criou um repositório :]

- Depois disso, crie uma pasta, abra o github, va na opção "clone git repository" vá no repositório que voce criou, vá na opção "code", copie o link e coloque na barra de pesquisa a cima. 

- nisso, selecione a pasta que voce criou antes. Agora, va na opção "terminal", depois na opção "abrir novo terminal" e escreva as linhas a baixo para criar o seu servidor. (não escreva a ultima linha, ela não vai rodar, voce tem que ir em "scr" e criar umarquivo app.ts manualmente)

```bash
npm init -y
npm install express cors sqlite3 sqlite
npm install --save-dev typescript nodemon ts-node @types/express @types/cors
npx tsc --init
mkdir src
touch src/app.ts
```

## Configuranado o `tsconfig.json`

- com o server criado, voce irá para a pasta "tsconfig.json" voce irá adicionar `"outDir": "./",` para `"outDir": "./dist",` e adicione a linha `"rootDir": "./src",`nas linhas 58 e 59  sem deixar como comentário e deve ficar mais ou menos assim:

```json
{
  "compilerOptions": {
    "target": "ES2017",
    "module": "commonjs",
    "outDir": "./dist",
    "rootDir": "./src",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true
  }
}
```

## Configurando o `package.json`
- agora, vá para a pasta "package.json" e substitua o que estiver dentro das chaves de "scripts" pelo o que está dentro das cheves deste código abaixo:

```json
"scripts": {
  "dev": "npx nodemon src/app.ts"
}
```

## Criando arquivo inicial do servidor

- vá para a pasta app.ts que voce havia criado antes e escreva o código abaixo:

```typescript
import express from 'express';
import cors from 'cors';

const port = 3333;
const app = express();

app.use(cors());
app.use(express.json());

app.get('/', (req, res) => {
  res.send('Hello World');
});

app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
```

## Inicializando o servidor

- abra  terminal novamente, e digite 'npm run dev' 
- E se tudo ocorrer bem, você verá a mensagem "Server running on port 3333" no terminal.

## Testando o servidor

- Abra o navegador e digite `http://localhost:3333`, você deverá ver a mensagem `Hello World`. Parabens voce agora tem um local host :D
