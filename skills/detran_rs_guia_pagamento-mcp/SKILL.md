---
name: detran_rs_guia_pagamento-mcp
description: Skill da REST API do DETRAN RS: Guia de Pagamento na MCP.AI: 1 endpoint em /api/detran_rs_guia_pagamento. DETRAN RS: Guia de Pagamento, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# DETRAN RS: Guia de Pagamento — REST API skill

Você tem acesso à **DETRAN RS: Guia de Pagamento** REST API na MCP.AI.

> DETRAN RS: Guia de Pagamento, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/detran_rs_guia_pagamento
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
curl -X POST https://api.mcp.ai/api/detran_rs_guia_pagamento/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"placa":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/detran_rs_guia_pagamento/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `detran_rs_guia_pagamento_consultar`

DETRAN RS: Guia de Pagamento, consulta em fonte oficial. _(POST /api/detran_rs_guia_pagamento/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `renavam` | string | Não | Parâmetro de consulta "renavam". |
| `placa` | string | Sim | Parâmetro de consulta "placa". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_detran_rs_guia_pagamento` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
