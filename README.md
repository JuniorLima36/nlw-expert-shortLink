# 🚀 Projeto short-links
Crie uma URL customizada que redirecione para outra página, Projeto desenvolvido no Evento Node na Prática Encurtador de URLs. 

## 🧊 Funcionalidades
- URLs originais e reduzidas salvas em base de dados Postgres;
- Métricas de acesso salvas em base de dados Redis;
- Bases de dados rodando localmente em containers Docker;

## 🛠️ Tecnologias
- Node.js
- Docker
- PostgreSQL
- Redis

## :clipboard: Clonando o repositório:

```sh
  git clone https://github.com/JuniorLima36/nlw-expert-shortLink.git
```

### ▶️ Rodando o App:
```sh
  docker compose up -d
  npm install
  npm run setup
  npm run dev
```

### :computer: Rotas HTTP
---
Cria uma nova URL.
#### POST <code>http://localhost:3333/api/links</code>


#### Request body
```json
{
  "code": "yourShortLink",
  "url": "https://github.com/JuniorLima36/yourShortLink"
}
```
---

Acessa URL curta (<code>http://localhost:3333/yourShortLink</code>), é redirecionado para url longa (<code>https://github.com/JuniorLima36/yourShortLink</code>). 

#### GET <code>http://localhost:3333/:code</code>
---

Retorna dados de acesso das URLs mais acessadas.
#### GET <code>http://localhost:3333/api/metrics</code>

#### Response body
```json
[
  {
    "shortLinkId": 1,
    "clicks": 4
  },
  {
    "shortLinkId": 2,
    "clicks": 1
  }
]
```
---