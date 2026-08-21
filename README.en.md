# Mercos

### Mercos for Claude, ChatGPT and AI agents

Sales force and rep ERP on Mercos via the official API. List orders, customers, products, price tables, payment terms, carriers, sellers and commissions, and create or update customers, products, orders and stock in natural language. Auth via a Company Token, generated in the Mercos account under My Account, System, Integration.

- 📊 **19 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Mercos`, URL `https://api.mcp.ai/p_mercos`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=mercos&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9tZXJjb3MifQ==)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=mercos&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_mercos%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_mercos
```

---

## 19 tools

| Tool | Description |
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

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_mercos` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
