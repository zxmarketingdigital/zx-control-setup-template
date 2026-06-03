---
description: Valida o setup contra as 12 regras invioláveis do ZX Control (roda localmente, sem internet).
---

Rode o validador local e me mostre o resultado de forma simples:

```bash
python3 scripts/validate.py --path .
```

Depois:
- Se aparecer **OK** → diga ao colaborador que está tudo certo e pode abrir o Pull Request.
- Se aparecer itens **BLOQUEIA** → corrija cada um você mesmo (seguindo a dica "como corrigir"),
  rode de novo, e repita até ficar OK. Explique em linguagem simples o que estava errado.
- Se aparecer só **avisos** → mostre ao colaborador e pergunte se quer ajustar antes do PR.

Nunca abra o PR com itens BLOQUEIA pendentes.
