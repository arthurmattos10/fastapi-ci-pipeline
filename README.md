# FastAPI CI Pipeline

Este projeto foi desenvolvido como atividade prática da disciplina Automação de Testes de Software, cursada no 5º semestre da graduação na Faculdade Impacta.

A proposta da atividade foi aplicar conceitos de Integração Contínua (CI/CD) utilizando GitHub Actions e FastAPI, simulando um fluxo profissional de desenvolvimento com testes automatizados, Pull Requests, proteção de branches e testes de integração.

O objetivo da atividade foi demonstrar, na prática, como pipelines automatizadas conseguem validar código, executar testes, proteger bran

O objetivo da atividade foi demonstrar, na prática, como pipelines automatizadas conseguem validar código, executar testes, proteger branches e garantir a qualidade da aplicação antes do merge.

---

# Tecnologias Utilizadas

* Python 3
* FastAPI
* Pytest
* GitHub Actions
* Git e GitHub

---

# Estrutura do Projeto

```text
.
├── .github/
│   └── workflows/
│       └── ci.yml
├── main.py
├── test_main.py
├── requirements.txt
└── .gitignore
```

---

# Funcionalidades da API

## Rota Inicial

```http
GET /
```

Resposta:

```json
{
  "mensagem": "API funcionando!"
}
```

---

## Rota de Soma

```http
GET /somar/{a}/{b}
```

Exemplo:

```http
GET /somar/10/20
```

Resposta:

```json
{
  "resultado": 30
}
```

---

## Rota de Multiplicação

```http
GET /multiplicar/{a}/{b}
```

Exemplo:

```http
GET /multiplicar/5/2
```

Resposta:

```json
{
  "resultado": 10
}
```

---

# Testes Automatizados

O projeto utiliza o Pytest para validar automaticamente o comportamento da API.

Os testes verificam:

* funcionamento da rota principal
* operação de soma
* operação de multiplicação
* respostas HTTP
* integridade do JSON retornado

---

# GitHub Actions

O pipeline CI/CD foi configurado utilizando GitHub Actions.

A automação executa:

1. Checkout do código
2. Configuração do Python
3. Instalação das dependências
4. Execução dos testes automatizados
5. Teste de integração com a API rodando no Runner

---

# Strategy Matrix

O workflow utiliza Strategy Matrix para testar múltiplas versões do Python automaticamente:

* Python 3.10
* Python 3.11
* Python 3.12

Isso garante compatibilidade da aplicação em diferentes ambientes.

---

# Proteção de Branch

Durante a atividade foi configurada proteção para a branch `main`, exigindo:

* Pull Request antes do merge
* aprovação dos testes automatizados
* sucesso do workflow `verificar-api`

---

# Teste de Integração

Além dos testes unitários, o pipeline também realiza um teste de integração.

A API é iniciada automaticamente dentro do GitHub Runner e são feitas requisições reais utilizando `curl`.

Exemplo:

```bash
curl -f http://localhost:8000/
curl -f http://localhost:8000/somar/10/20
```

---

# Como Executar Localmente

## Instalar dependências

```bash
pip install -r requirements.txt
```

---

## Executar a API

```bash
fastapi dev main.py
```

---

## Executar os testes

```bash
pytest test_main.py
```

---

# Objetivo da Atividade

Esta atividade teve como objetivo praticar:

* Integração Contínua (CI)
* GitHub Actions
* Testes Automatizados
* Proteção de Branches
* Pull Requests
* Strategy Matrix
* Testes de Integração
* Fluxo profissional de desenvolvimento

---

# Autor

Arthur Mattos
