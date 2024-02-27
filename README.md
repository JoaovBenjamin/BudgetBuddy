# BudgetBuddy
API Rest do Projeto BudgetBuddy

## Requisitos
- [ ] CRUD de Categorias
- [ ] CRUD de Movimentações
- [ ] CRUD de Usuarios
- [ ] Autenticação
- [ ] Dashboard

## Documentação

### Endpoints


.[Listar Categoria](#listar-categorias)  

.[Apagar Categoria](#apagar-categoria)  

.[Detalhar  Categoria](#detalhar-categoria)

.[Cadastrar  Categoria](#cadastrar-categoria)

.[Atualizar Categoria](#atualizar-categoria)


### Listar Categorias
`GET`  /categoria

Retorna um array com todas as categorias cadastradas pelo usuário atual.

#### Exemplo de Resposta

```js
[
    {
        "id": 1,
        "nome" :  "Alimentacao",
        "icone" : "fast-food",
    }
]
```

#### Códigos de Resposta  HTTP
 
|codigo|descrição|
|--- | --- |
[200] Categorias retornadas com sucesso
[401]  Não autorizado. Realize a autenticação em /login

### Cadastrar Categoria
`POST` /categoria

Cadastra categoria com dados enviados no corpo da requisição

#### Corpo da Requisição

|campo | tipo | obrigatório| descrição
|------|------|------------|-----------
|nome|string|✔| nome da categoria
|icone|string|✖| O nome do icone conforme biblioteca Material Icons

```js
[
    {
        "nome" : "Alimentção",
        "icone" : "fast-food",
    }
]
```

#### Exemplo de Resposta
```js
[
    {
        "id":1,
        "nome":"Alimentação",
        "icone":"fast-food"
    }
]
```

#### Código de Requisições

| codigo | descrição |
|--------|-----------|
[201] Categoria cadastrada com sucesso
[400] Erro na validação. Verifique os dados enviados
[401]  Não autorizado. Realize a autenticação em /login

### Apagar Categoria
`DELETE`  /categorias/`{id}`

Apaga categoria com o `id` informado no parâmetro da URL.

#### Código de Resposta 
|código|descrição|
|-----|----------|
[204] A categoria foi apagada com sucesso|
[401] Não autorizado. Realize a autenticação em /login

### Detalhar Categoria
`GET`  /categorias/`{id}`

Retorna os dados da categoria com o `id` informado na URL

#### Exemplo de Resposta
```js
//Requisição da categoria 1
[
    {
        "id":1,
        "nome":"Alimentação",
        "icone":"fast-food"
    }
]
```

#### Codigo de Resposta
|Codigo|Descrição|
|------|----------|
[200] Dados retornados com sucesso
[401]  Não autorizado. Realize a autenticação em /login
[404] A categoria não existe

### Atualizar Categoria
`PUT` /categorias/`{id}`

Atualiza as informações da categoria com o `id` presente nos parâmetros da URL

#### Corpo da Requisição

|campo | tipo | obrigatório| descrição
|------|------|------------|-----------
|nome|string|✔| nome da categoria
|icone|string|✔| O nome do icone conforme biblioteca Material Icons

```js
[
    {
        "nome" : "Alimentção",
        "icone" : "fast-food",
    }
]
```

#### Exemplo de Resposta
```js
[
    {
        "id":1,
        "nome":"Alimentação",
        "icone":"fast-food"
    }
]
```
#### Código de Requisições

| codigo | descrição |
|--------|-----------|
[200] Categoria cadastrada com sucesso
[400] Erro na validação. Verifique os dados enviados
[401]  Não autorizado. Realize a autenticação em /login
[404]  A categoria não foi encontrada.