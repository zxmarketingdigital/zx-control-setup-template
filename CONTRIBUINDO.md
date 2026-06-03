# Como criar/atualizar um Setup do ZX Control — Guia do Colaborador

> Você **não precisa saber programar**. Você conversa com o Claude em português, e ele
> faz todo o trabalho técnico. Este guia é o passo a passo da primeira vez.

---

## Antes de começar (só uma vez)

1. Abra o site **https://claude.ai/code** no navegador.
2. Faça login com o usuário e a senha que o Rafael te passou.
3. Na primeira vez, ele vai pedir pra **conectar o GitHub** — clique em conectar e
   autorize. (O GitHub é onde os setups ficam guardados.)

Pronto. Agora você nunca mais precisa repetir isso.

---

## Criar um Setup NOVO

> O **Rafael** cria o repositório novo pra você (leva 30 segundos e já deixa tudo
> protegido). Ele te manda o link. Você começa direto no passo 2.

1. _(Rafael)_ Cria o repo a partir do template e roda o bootstrap de proteções.
2. Abra o **claude.ai/code** e abra o repositório que o Rafael te mandou.
3. Escreva pro Claude, em português, algo como:

   > "Vamos criar o Setup 10 do ZX Control sobre **[tema que o Rafael passou]**.
   > Leia o CLAUDE.md e o setup.config.json e me conduza."

4. O Claude vai te fazer algumas perguntas e montar tudo. **Deixe ele trabalhar.**
5. Quando ele terminar, peça: **"valida o setup"**. Ele roda a checagem e corrige o que
   precisar.
6. Por fim, peça: **"abre o Pull Request"**. Ele cria o pedido de revisão.
7. **Avise o Rafael** que o PR está pronto (WhatsApp/onde vocês falam).

É isso. O Rafael revisa, aprova e publica pros alunos. Você **não publica nada** — sua
parte termina no Pull Request.

---

## Atualizar um Setup que JÁ existe

1. No **claude.ai/code**, abra o repositório do setup que você quer mexer
   (ex.: `zx-control-setup9-...`).
2. Escreva pro Claude o que mudar, ex.:

   > "Neste setup, corrija **[o que for]** / adicione **[o que for]**.
   > Leia o CLAUDE.md antes."

3. Deixe ele fazer. Depois: **"valida o setup"** → **"abre o Pull Request"**.
4. Avise o Rafael.

---

## Perguntas comuns

**"Preciso usar o terminal / digitar comandos?"**
Não. Você só conversa com o Claude. Ele cuida do terminal, do git e de tudo.

**"E se a validação reclamar de alguma coisa?"**
Peça pro Claude corrigir: *"corrige os erros que a validação apontou"*. Ele resolve.

**"Posso quebrar a produção / os alunos?"**
Não. Você só abre um pedido (Pull Request). Nada vai pro ar até o Rafael aprovar.

**"O que é um Pull Request?"**
É um "pedido de revisão": você propõe uma mudança, e o Rafael decide se entra. Pense nele
como mandar um documento pra aprovação.

**"Travei / não sei o que fazer."**
Escreva pro Claude: *"estou perdido, me explica o próximo passo de forma simples"*.
Se ainda assim travar, chama o Rafael.

---

## As regras (o Claude já conhece — você não precisa decorar)

O Claude segue 12 regras automaticamente e a validação confere todas. Você não precisa
saber nenhuma delas de cor — só rodar **"valida o setup"** antes de abrir o PR.
