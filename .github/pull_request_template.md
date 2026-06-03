## O que este PR faz

<!-- Descreva em 1-2 frases: criou o Setup N? atualizou o quê? -->

## Checklist das 12 regras (o CI confere, mas confirme)

- [ ] Python sem `X | None` e sem `match/case` (compatível 3.9)
- [ ] Sem `open("~/...")` — usei `Path.home()`
- [ ] Dashboard sem `fetch()` (dados inline)
- [ ] Só um `docs/index.html` + `docs/_redirects` presente
- [ ] Nenhuma senha/chave/token escrita no código
- [ ] Nenhum `.env` real commitado (só `.env.example`)
- [ ] Nenhum caminho/ID interno da ZX LAB no repo
- [ ] Tem `README.md`, `CLAUDE.md`, `MASTERCLASS.md`, `setup/check_prerequisites.py`
- [ ] Copy fala de benefício, sem preço, CTA único → mission-control

## Para o Rafael (publicação)

<!-- Número do setup, tema, e qualquer coisa que ele precise saber pra publicar. -->
