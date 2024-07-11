# Iniciando um projeto Node.js com TypeScript
abra o github e crie um repositório,para criar um repositório, va na barra da esquerda, clique no botao "new", vá em "repository name" e de um nome a seu seu repositório, depois, vá para a opção "add a README file" e a habilite. Após isso, apenas clique na opção "create repository" e parabens, voce criou um repositório :]
Depois disso, crie uma pasta, abra o github, va na opção "clone git repository" vá no repositório que voce criou, vá na opção "code", copie o link e coloque na barra de pesquisa a cima. nisso, selecione a pasta que voce criou antes. agora, va na opção terminal, depois na opção "abrir novo terminal" e escreva as linhas a baixo para criar o seu servido

```bash
npm init -y
npm install express cors sqlite3 sqlite
npm install --save-dev typescript nodemon ts-node @types/express @types/cors
npx tsc --init
mkdir src
touch src/app.ts
```

## Configuranado o `tsconfig.json`

Mude a linha ```"outDir": "./",``` para ```"outDir": "./dist",``` e adicione a linha ```"rootDir": "./src",```, seu arquivo de configuração do compilador do TypeScript ficará mais ou menos assim.

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

Adicione o seguinte script ao seu `package.json`

```json
"scripts": {
  "dev": "npx nodemon src/app.ts"
}
```

## Criando arquivo inicial do servidor

Adicione o seguinte código ao arquivo `src/app.ts`

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

```bash
npm run dev
```

Se tudo ocorrer bem, você verá a mensagem `Server running on port 3333` no terminal.

## Testando o servidor

Abra o navegador e acesse `http://localhost:3333`, você verá a mensagem `Hello World`.
  res.json(users);
});
```
