# Desafio Carrefour - Testes de API

Projeto desenvolvido para automatizar testes da API **ServeRest** utilizando **Postman**, **Newman** e **GitHub Actions**, simulando um fluxo completo de testes de API em um pipeline de Integração Contínua (CI).

## Tecnologias utilizadas

- Postman
- Newman
- Node.js
- GitHub Actions
- Git
- GitHub

---

# Estrutura do projeto

```
.
├── .github
│   └── workflows
│       └── api-tests.yml
├── Collections
│   └── Desafio Carrefour.postman_collection.json
├── Environment
│   └── ServeRest_env.postman_environment.json
└── README.md
```

---

# Cenários automatizados

A collection executa um fluxo completo da API ServeRest.

### Login

- Realiza autenticação
- Captura o token automaticamente

### Usuários

- Cadastro de usuário
- Listagem de usuários
- Consulta de usuário por ID
- Alteração de usuário
- Exclusão de usuário

---

# Validações implementadas

Durante a execução dos testes são realizadas validações como:

- Status Code
- Tempo de resposta
- Estrutura do Body
- Mensagens retornadas pela API
- Captura de variáveis de ambiente
- Encadeamento entre requisições

Exemplos:

- Status Code 200
- Status Code 201
- Resposta inferior a 1000 ms
- Existência do campo `_id`
- Mensagem "Cadastro realizado com sucesso"

---

# Execução local

## Pré-requisitos

Ter instalado:

- Git
- Node.js
- Newman

Caso não tenha o Newman:

```bash
npm install -g newman
```

---

## Clonar o projeto

```bash
git clone https://github.com/MarcoQAestudos/Desafio-Carrefour-Teste-API
```

Entrar na pasta:

```bash
cd Desafio-Carrefour-Teste-API
```

---

## Executar os testes

```bash
newman run "Collections/Desafio Carrefour.postman_collection.json" -e "Environment/ServeRest_env.postman_environment.json"
```

Ao final será exibido um relatório semelhante a:

```
Iterations
Requests
Test Scripts
Assertions

PASS
FAIL
```

---

# Integração Contínua (CI)

O projeto possui uma pipeline utilizando **GitHub Actions**.

Sempre que um **push** é realizado na branch **main**, o GitHub:

1. Cria uma máquina virtual Ubuntu
2. Faz checkout do projeto
3. Instala o Node.js
4. Instala o Newman
5. Executa automaticamente todos os testes da Collection

Workflow utilizado:

```
.github/workflows/api-tests.yml
```

---

# Executando a pipeline manualmente

Além da execução automática via **push**, a pipeline pode ser executada manualmente.

No GitHub:

**Actions**

↓

**API Tests**

↓

**Run workflow**

↓

**Run workflow**

O GitHub executará todos os testes automaticamente.

---

# Como reproduzir o projeto

1. Faça um Fork deste repositório (opcional).

2. Clone o projeto:

```bash
git clone https://github.com/MarcoQAestudos/Desafio-Carrefour-Teste-API
```

3. Entre na pasta:

```bash
cd Desafio-Carrefour-Teste-API
```

4. Instale o Newman:

```bash
npm install -g newman
```

5. Execute:

```bash
newman run "Collections/Desafio Carrefour.postman_collection.json" -e "Environment/ServeRest_env.postman_environment.json"
```

---

# Pipeline GitHub Actions

Sempre que houver um novo commit na branch **main**, a pipeline será iniciada automaticamente.

É possível acompanhar a execução em:

**GitHub → Actions → API Tests**

Lá estarão disponíveis:

- Histórico das execuções
- Tempo de execução
- Logs completos
- Resultado dos testes

---

# Repositório

```
[SEU_LINK_DO_REPOSITORIO](https://github.com/MarcoQAestudos/Desafio-Carrefour-Teste-API/actions)
```

---

# Autor

Marco Rodrigues

Analista de Testes | QA | Automação de Testes | API Testing
