# Ferramentas

Mercos expõe 19 ferramentas.

### 1. `mercos_list_accounts`
**Input**: `account` (opcional)

Lista as empresas (CompanyToken) Mercos conectadas a este install, com id e label.

### 2. `mercos_list_produtos`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista produtos cadastrados (GET /v1/produtos).

### 3. `mercos_list_clientes`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista clientes (GET /v1/clientes).

### 4. `mercos_list_pedidos`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista pedidos (GET /v2/pedidos).

### 5. `mercos_list_tabelas_preco`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista tabelas de preço (GET /v1/tabelas_preco).

### 6. `mercos_list_categorias`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista categorias de produtos (GET /v1/categorias).

### 7. `mercos_list_condicoes_pagamento`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista condições de pagamento (GET /v1/condicoes_pagamento).

### 8. `mercos_list_transportadoras`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista transportadoras (GET /v1/transportadoras).

### 9. `mercos_list_usuarios`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista vendedores/usuários (GET /v1/usuarios).

### 10. `mercos_list_comissoes`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista comissões (GET /v1/comissoes).

### 11. `mercos_list_titulos`
**Input**: `alterado_apos` (opcional), `filters` (opcional), `account` (opcional)

Lista títulos financeiros (GET /v1/titulos).

### 12. `mercos_create_cliente`
**Input**: `data`, `account` (opcional)

Inclui cliente(s) (POST /v1/clientes).

### 13. `mercos_update_cliente`
**Input**: `id`, `data`, `account` (opcional), `ids` (opcional)

Altera um cliente (PUT /v1/clientes/{id}).

### 14. `mercos_create_produto`
**Input**: `data`, `account` (opcional)

Inclui produto(s) (POST /v1/produtos).

### 15. `mercos_update_produto`
**Input**: `id`, `data`, `account` (opcional), `ids` (opcional)

Altera um produto (PUT /v1/produtos/{id}).

### 16. `mercos_create_pedido`
**Input**: `data`, `account` (opcional)

Inclui um pedido (POST /v2/pedidos).

### 17. `mercos_update_pedido`
**Input**: `id`, `data`, `account` (opcional), `ids` (opcional)

Altera um pedido (PUT /v2/pedidos/{id}).

### 18. `mercos_ajustar_estoque`
**Input**: `data`, `account` (opcional)

Ajusta o estoque de produtos em lote (POST /v1/ajustar_estoque_em_lote).

### 19. `mercos_create_tabela_preco`
**Input**: `data`, `account` (opcional)

Inclui uma tabela de preço (POST /v1/tabelas_preco).

## Prompts de exemplo

```
Liste os pedidos alterados desde ontem
Cadastre um cliente novo a partir destes dados
Liste as comissões do vendedor com colaborador_id 123
```
