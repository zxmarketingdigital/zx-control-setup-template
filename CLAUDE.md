# Instruções para o Claude — Criar/Atualizar um Setup do ZX Control

> Você (Claude) está ajudando um **colaborador da ZX LAB** a criar ou atualizar um
> **Setup do ZX Control**. O colaborador **pode não ser programador**. Faça o trabalho
> técnico você mesmo, explique em linguagem simples, uma etapa por vez, e **nunca**
> peça pra ele digitar comando no terminal.

## O que é um "Setup"

Um Setup é um módulo semanal que o aluno do ZX Control clona e instala no Claude Code
dele. Cada Setup é **este repositório**: um conjunto de arquivos (guia, scripts de
instalação, dashboard) que ensina o aluno a montar uma automação.

## Seu fluxo de trabalho

1. **Leia `setup.config.json`** na raiz. Ele tem os dados do setup (número, tema, cor).
   Se estiver com valores de exemplo, pergunte ao colaborador os dados e preencha.
2. **Crie/edite o conteúdo** seguindo as REGRAS abaixo. Os arquivos-base já existem como
   modelo — personalize-os para o tema do setup.
3. **Valide** rodando o comando `/validar-setup` (ou `python3 scripts/validate.py --path .`).
   Corrija tudo que aparecer como **BLOQUEIA**.
4. **Salve numa branch nova** (nunca direto na `main`) e **abra um Pull Request**.
5. **Avise o colaborador** que o PR está pronto e que o Rafael vai revisar e publicar.

Você nunca publica em produção — quem faz isso é o Rafael, na máquina dele.

## As 12 REGRAS invioláveis (o validador checa todas)

**Python (os alunos têm Python 3.9):**
1. Nunca `X | None` → use `Optional[X]` (`from typing import Optional`).
2. Nunca `match/case` → use `if/elif`.
3. Nunca `open("~/...")` → use `Path.home() / "..."`.

**Dashboards (`docs/`):**
4. Nunca `fetch()` num dashboard — ele abre via `file://` e quebra. Injete os dados
   inline no HTML (`const _DATA = {...}`).
5. Só um `docs/index.html` (sem duplicar páginas). `docs/_redirects` sempre presente.

**Segurança:**
6. Nunca escreva senha/chave/token direto no código. Use `.env` (já no `.gitignore`)
   e leia com `os.environ.get("VAR")` (Python) ou `Deno.env.get("VAR")` (Edge Function).
7. Nunca commite um arquivo `.env` real — só `.env.example` com valores vazios.
8. Nunca coloque caminhos ou IDs internos da ZX LAB neste repo (ele é **público**).
   O diretório `~/.operacao-ia/config/` é do próprio aluno — esse pode usar.

**Banco de dados (se houver Edge Function):**
9. Filtre acesso por `purchase_date` (data da compra), nunca por `product_name ILIKE`.

**Estrutura e instalação:**
10. O repo precisa ter sempre: `README.md`, `CLAUDE.md`, `MASTERCLASS.md`,
    `setup/check_prerequisites.py`.
11. `install.sh` (se existir) faz backup com timestamp — nunca `rm -rf` na pasta do aluno.

**Copy (texto pro aluno):**
12. Fale de **resultado/benefício**, não de termos técnicos. Sem preço, sem mencionar
    versão anterior. Um único CTA no final → `https://zxlab.com.br/mission-control`.

## NÃO faça

- Não rode disparo de WhatsApp/email, não faça deploy, não toque em produção.
- Não torne o repositório privado.
- Não invente credenciais nem peça as do Rafael.

## Estrutura esperada do repo

```
README.md                      Guia do aluno (o que ele vai conseguir + como começar)
CLAUDE.md                      Este arquivo (instruções pro Claude do aluno também)
MASTERCLASS.md                 Roteiro da aula (placeholders BUNNY_GUID — Rafael preenche)
setup/check_prerequisites.py   1ª coisa que o Claude do aluno roda (valida ambiente)
setup/setup_*.py               Um script por etapa (idempotente, lê ~/.operacao-ia/config/)
docs/index.html                Dashboard local (dados inline, sem fetch)
docs/_redirects                Roteamento (/  /index.html  200)
.env.example                   Modelo de variáveis (sem valores reais)
```
