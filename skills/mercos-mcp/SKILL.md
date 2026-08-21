---
name: mercos-mcp
description: Skill da REST API do Mercos na MCP.AI: 19 endpoints em /api/mercos. Força de vendas e ERP de representantes na Mercos via API oficial. Liste pedidos, clientes, produtos, tabelas de preço, condições de pagamento, transportadoras, vendedores e comissões, e cadastre ou atualize clientes, produtos, pedidos e estoque por linguagem natural. Autenticação por Company Token, gerado na conta Mercos em Minha Conta, Sistema, Integração. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Mercos — REST API skill

Você tem acesso à **Mercos** REST API na MCP.AI.

> Força de vendas e ERP de representantes na Mercos via API oficial. Liste pedidos, clientes, produtos, tabelas de preço, condições de pagamento, transportadoras, vendedores e comissões, e cadastre ou atualize clientes, produtos, pedidos e estoque por linguagem natural. Autenticação por Company Token, gerado na conta Mercos em Minha Conta, Sistema, Integração.

## Base URL

```
https://api.mcp.ai/api/mercos
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/mercos/ajustar/estoque \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"data":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/mercos/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (19)

#### `mercos_ajustar_estoque`

Ajusta o estoque de produtos em lote (POST /v1/ajustar_estoque_em_lote). _(POST /api/mercos/ajustar/estoque)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_create_cliente`

Inclui cliente(s) (POST /v1/clientes). _(POST /api/mercos/create/cliente)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_create_pedido`

Inclui um pedido (POST /v2/pedidos). _(POST /api/mercos/create/pedido)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_create_produto`

Inclui produto(s) (POST /v1/produtos). _(POST /api/mercos/create/produto)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_create_tabela_preco`

Inclui uma tabela de preço (POST /v1/tabelas_preco). _(POST /api/mercos/create/tabela/preco)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_accounts`

Lista as empresas (CompanyToken) Mercos conectadas a este install, com id e label. _(POST /api/mercos/list/accounts)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_categorias`

Lista categorias de produtos (GET /v1/categorias). _(POST /api/mercos/list/categorias)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_clientes`

Lista clientes (GET /v1/clientes). _(POST /api/mercos/list/clientes)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_comissoes`

Lista comissões (GET /v1/comissoes). _(POST /api/mercos/list/comissoes)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_condicoes_pagamento`

Lista condições de pagamento (GET /v1/condicoes_pagamento). _(POST /api/mercos/list/condicoes/pagamento)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_pedidos`

Lista pedidos (GET /v2/pedidos). _(POST /api/mercos/list/pedidos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_produtos`

Lista produtos cadastrados (GET /v1/produtos). _(POST /api/mercos/list/produtos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_tabelas_preco`

Lista tabelas de preço (GET /v1/tabelas_preco). _(POST /api/mercos/list/tabelas/preco)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_titulos`

Lista títulos financeiros (GET /v1/titulos). _(POST /api/mercos/list/titulos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_transportadoras`

Lista transportadoras (GET /v1/transportadoras). _(POST /api/mercos/list/transportadoras)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_list_usuarios`

Lista vendedores/usuários (GET /v1/usuarios). _(POST /api/mercos/list/usuarios)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `alterado_apos` | string | Não | Cursor de alteração no padrão ISO AAAA-MM-DDTHH:MM:SS (ex.: 2026-01-01T00:00:00). Retorna registros alterados após esse instante; pagine repetindo com o `ultima_alteracao` do último item. |
| `filters` | string | Não | Parâmetros extras de query como JSON string, mesclados na requisição (ex.: {"colaborador_id":123} em comissões). |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |

#### `mercos_update_cliente`

Altera um cliente (PUT /v1/clientes/{id}). _(POST /api/mercos/update/cliente)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | ID do registro na Mercos. |
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercos_update_pedido`

Altera um pedido (PUT /v2/pedidos/{id}). _(POST /api/mercos/update/pedido)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | ID do registro na Mercos. |
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

#### `mercos_update_produto`

Altera um produto (PUT /v1/produtos/{id}). _(POST /api/mercos/update/produto)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `id` | string | Sim | ID do registro na Mercos. |
| `data` | string | Sim | Corpo da requisição como JSON string. Pode ser um objeto único ou um array (lote). Use os nomes de campo do JSON da doc da Mercos. |
| `account` | string | Não | Quando há múltiplas empresas Mercos conectadas: id ou label da conexão. Veja mercos_list_accounts. |
| `ids` | string[] | Não | Bulk mode: multiple values for id |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_mercos` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
