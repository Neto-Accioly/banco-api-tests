# banco-api-tests

## Objetivo

Este projeto realiza testes automatizados na API REST do [banco-api](https://github.com/juliodelimas/banco-api), validando suas funcionalidades e contribuindo a qualidade de suas operações.

## Stack utilizada

- **Linguagem:** JavaScript (Node.js)
- **Framework de testes:** [Mocha](https://mochajs.org/)
- **Biblioteca de requisições HTTP:** [Supertest](https://github.com/ladjs/supertest)
- **Biblioteca de asserções:** [Chai](https://www.chaijs.com/)
- **Relatórios de testes:** [Mochawesome](https://github.com/adamgruber/mochawesome)
- **Gerenciamento de variáveis de ambiente:** [dotenv](https://github.com/motdotla/dotenv)

## Estrutura de diretórios

```
BANCO-API-TESTS/
├── fixtures/ # Arquivos JSON com dados reutilizáveis para os testes
│ ├── postLogin.json # Dados de entrada para testes de login
│ └── postTransferencias.json# Dados de entrada para testes de transferência
├── helpers/ # Funções auxiliares que evitam repetição de código
│ └── autenticacao.js # Função para lidar com autenticação via token
├── mochawesome-report/ # Relatórios gerados automaticamente após os testes
│ ├── assets/ # Arquivos de estilo e recursos visuais do relatório
│ └── mochawesome.html # Relatório visual em HTML
│ └── mochawesome.json # Relatório em formato JSON
├── node_modules/ # Dependências do projeto (instaladas via npm)
├── test/ # Scripts de teste automatizado
│ ├── login.test.js # Casos de teste para login
│ └── transferencia.test.js # Casos de teste para transferências
├── .env # Variáveis de ambiente (como token e baseURL)
├── .gitignore # Arquivos e pastas ignorados pelo Git
├── package-lock.json # Registro exato das versões instaladas das dependências
├── package.json # Configuração do projeto e lista de dependências
└── README.md # Documentação do projeto
```

## Formato do arquivo `.env`

Antes de rodar os testes, crie um arquivo chamado `.env` na raiz do projeto com o seguinte conteúdo:

```
BASE_URL=http://localhost:3000
```

Substitua `http://localhost:3000` pela URL onde a API `banco-api` está rodando.

## Comandos para execução

Instale as dependências:

```bash
npm install
```

Execute todos os testes:

```bash
npm test
```

Geração automática do relatório HTML:

- Após executar `npm test`, o relatório será gerado dentro da pasta `mochawesome-report/`.

Sugestão: para executar os testes e abrir o relatório HTML automaticamente, adicione um script no `package.json`:

```json
"scripts": {
  "test:report": "npm test && open mochawesome-report/mochawesome.html"
}
```

(Em Windows, substitua `open` por `start`.)

## Dependências utilizadas e suas documentações

- [Mocha](https://mochajs.org/) - Framework de execução de testes
- [Supertest](https://github.com/ladjs/supertest) - Biblioteca para chamadas HTTP
- [Chai](https://www.chaijs.com/) - Biblioteca de asserções
- [Mochawesome](https://github.com/adamgruber/mochawesome) - Geração de relatórios em HTML
- [dotenv](https://github.com/motdotla/dotenv) - Gerenciamento de variáveis de ambiente
