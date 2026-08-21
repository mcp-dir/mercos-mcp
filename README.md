# Mercos

### Mercos para Claude, ChatGPT e agentes de IA

Força de vendas e ERP de representantes na Mercos via API oficial. Liste pedidos, clientes, produtos, tabelas de preço, condições de pagamento, transportadoras, vendedores e comissões, e cadastre ou atualize clientes, produtos, pedidos e estoque por linguagem natural. Autenticação por Company Token, gerado na conta Mercos em Minha Conta, Sistema, Integração.

- 📊 **19 ferramentas**
- ✏️ **Leitura e escrita**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Mercos` e **URL** `https://api.mcp.ai/p_mercos`.

### Cursor

[➕ Instalar Mercos no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=mercos&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9tZXJjb3MifQ==)

### VS Code (Copilot Chat)

[➕ Instalar Mercos no VS Code](vscode:mcp/install?name=mercos&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_mercos%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_mercos
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Liste os pedidos alterados desde ontem
Cadastre um cliente novo a partir destes dados
Liste as comissões do vendedor com colaborador_id 123
```

---

## 19 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `mercos_list_accounts` | Lista as empresas (CompanyToken) Mercos conectadas a este install, com id e label. |
| `mercos_list_produtos` | Lista produtos cadastrados (GET /v1/produtos). |
| `mercos_list_clientes` | Lista clientes (GET /v1/clientes). |
| `mercos_list_pedidos` | Lista pedidos (GET /v2/pedidos). |
| `mercos_list_tabelas_preco` | Lista tabelas de preço (GET /v1/tabelas_preco). |
| `mercos_list_categorias` | Lista categorias de produtos (GET /v1/categorias). |
| `mercos_list_condicoes_pagamento` | Lista condições de pagamento (GET /v1/condicoes_pagamento). |
| `mercos_list_transportadoras` | Lista transportadoras (GET /v1/transportadoras). |
| `mercos_list_usuarios` | Lista vendedores/usuários (GET /v1/usuarios). |
| `mercos_list_comissoes` | Lista comissões (GET /v1/comissoes). |
| `mercos_list_titulos` | Lista títulos financeiros (GET /v1/titulos). |
| `mercos_create_cliente` | Inclui cliente(s) (POST /v1/clientes). |
| `mercos_update_cliente` | Altera um cliente (PUT /v1/clientes/{id}). |
| `mercos_create_produto` | Inclui produto(s) (POST /v1/produtos). |
| `mercos_update_produto` | Altera um produto (PUT /v1/produtos/{id}). |
| `mercos_create_pedido` | Inclui um pedido (POST /v2/pedidos). |
| `mercos_update_pedido` | Altera um pedido (PUT /v2/pedidos/{id}). |
| `mercos_ajustar_estoque` | Ajusta o estoque de produtos em lote (POST /v1/ajustar_estoque_em_lote). |
| `mercos_create_tabela_preco` | Inclui uma tabela de preço (POST /v1/tabelas_preco). |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Sub-processadores**: Mercos, o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_mercos`.


---

## Suporte

- 📧 [mercos@mcp.ai](mailto:mercos@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/mercos-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_mercos` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
