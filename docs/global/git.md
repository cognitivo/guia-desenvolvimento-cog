# O git 🌳

## **Por que o Git existe?**

O Git é uma ferramenta essencial para o nosso trabalho. Este documento institucionaliza as boas práticas e o processo que **deve ser seguido em todos os projetos** da Cognitivo.

Nosso objetivo é garantir que o código seja padronizado, que tenhamos um histórico claro das alterações e que a nossa operação seja eficaz e previsível, eliminando riscos como a perda de código. Ter um processo bem definido nos permite, acima de tudo, cobrar a sua utilização e manter um alto padrão de qualidade.

## **Padronização de Commits (Commits Semânticos)**

A padronização dos commits é obrigatória e tem como objetivo trazer um histórico claro e rastreável para o projeto. Um commit deve representar **uma unidade lógica de trabalho**, ou seja, uma etapa de uma tarefa completa que pode ser entendida de forma isolada.

Para isso, seguimos o padrão de commits semânticos:

```plaintext
<tipo>(escopo opcional): <descrição>
```

Onde cada estrutura tem uma função específica:

- **type:** indica o tipo da alteração realizada no commit. Os tipos que utilizamos são:
    
    - **feat:** Uma nova funcionalidade (feature).
    - **fix:** Uma correção de um bug (bug fix).
    - **docs:** Alterações na documentação.
    - **style:** Formatação de código que não altera a lógica (espaços, ponto e vírgula, etc.).
    - **refactor:** Refatoração de código que não corrige um bug nem adiciona uma funcionalidade, somente melhora a legibilidade ou a estrutura do código.
    - **test:** Adição ou correção de testes.
    - **chore:** Outras alterações que não modificam o código-fonte ou testes (ex: atualização de dependências).

- **scope:** (Opcional) Escopo da alteração (ex: api, modelo, auth).

- **description:** Descrição curta e objetiva do que foi feito.

> 💡 **Dica**: Utilize o **AI Docs** para gerar mensagens de commit claras e padronizadas a partir das suas alterações.

Lembre-se: Seu commit é uma conversa com o futuro. **Com você mesmo daqui a 6 meses e com seus colegas que nunca viram esse código.** Uma mensagem ambígua é como dar direções sem pontos de referência.

#### Exemplos:

* **Bons:** ✅

    - `feat: melhora do desempenho com o carregamento lento das imagens`

    - `feat(auth): implementa autenticação JWT`

    - `fix: correção do treinamento do modelo, fazendo o fit na porção correta do treinamento`

    - `chore: inserção de dependência faltando - scikit-learn`

    - `docs: atualização do README com instruções de instalação`

    - `fix(api): corrige erro no endpoint de usuários`

    - `style: aplicação de formatador de código black`

- **Ruins (Exemplos reais):** ❌

    - `add api deploy`

    - `Mudança nos modelos e inserção documentação`

    - `improve notebook`

    - `Documentacao tecninca do projeto`

    - `quickfixes`

    - `ajustando`

    - `fix_trial`

## **Trabalhando com Branches**

Nossa estrutura de branches é desenhada para garantir estabilidade e organização.

### Nomenclatura Padrão

Utilizamos os seguintes prefixos para nomear as branches:

* **`feature/<nome-da-tarefa>`:** Para novas funcionalidades.

* **`fix/<nome-da-tarefa>`:** Para correção de bugs.

O nome deve ser claro, conciso e, se possível, relacionado à tarefa no ClickUp (ex: `feature/jwt-auth-api`).

### Papel das Branchs principais

Todo repositório terá, por padrão, as seguintes branches principais:

* **`main`:** É a nossa branch principal, estável e que reflete o código em produção. Ela é protegida e não deve receber commits diretos. Todo código que chega nela já foi testado e validado, além de chegar somente por meio de PRs da `develop`.

* **`develop`:** É a branch de integração e desenvolvimento. Todo novo trabalho (features e fixes) deve ser mergeado nela primeiro. Ela representa o estado mais atual do que estará no próximo lançamento.


## **Pull Requests (PRs) e Revisão de Código**

### Os PRs

Se os seus commits são a história do seu trabalho, o Pull Request (PR) é o momento em que você convida outros para lerem, contribuírem e validarem essa história. É o coração do nosso processo colaborativo, onde a qualidade é forjada em conjunto.

#### Preparando o PR: o título e o template

Antes de chamar os revisores, precisamos arrumar a casa. Um PR bem-estruturado acelera a revisão e melhora a comunicação.

- **O Título é a parte fundamental:**

    - O formato `Título descritivo do PR (#ID_DA_TASK_NO_CLICKUP)` **não é burocracia, é um GPS.** Ele conecta instantaneamente seu código a uma tarefa no ClickUp, dando contexto a todos sobre o porquê daquela alteração existir.

- **O Template é a história:**

    - Pense no template do PR como uma história para uma boa conversa. Preenchê-lo corretamente **garante que ninguém perca tempo** tentando adivinhar o que está acontecendo.

        - **Contexto:** Descreva o problema ou a necessidade que motivou o seu trabalho.

        - **Alterações Realizadas:** Liste de forma clara e objetiva as principais mudanças que você implementou.

        - **Itens Relacionados:** Adicione o link para a tarefa no ClickUp e qualquer outra documentação que ajude a entender o cenário completo.


O PR deve sempre seguir a estrutura abaixo:

```markdown
# Título descritivo do PR (#ID_DA_TASK_NO_CLICKUP)

## Contexto

Descreva o problema ou a necessidade que motivou o seu trabalho.

## Alterações Realizadas

Liste de forma clara e objetiva as principais mudanças que você implementou.

## Itens Relacionados

Adicione o link para a tarefa no ClickUp e qualquer outra documentação que ajude a entender o cenário completo.

```

> ⚠️ **Fique ligado:** os PRs deve ser sucintos e focados em **uma única tarefa**, PRs muitos grandes podem ser demorados para serem revisados

> 📒 **Conteúdos extras:** [The anatomy of a perfect pull request | by Hugo Dias](https://hugooodias.medium.com/the-anatomy-of-a-perfect-pull-request-567382bb6067)


### Reviews

A revisão de código não é um teste, é um diálogo. É a chance de aprender, ensinar e, principalmente, **garantir que estamos entregando o nosso melhor.**

Para guiar essa conversa, o revisor se baseia em **3 Pilares de Qualidade:**

- **Rastreabilidade:** O PR está corretamente conectado a uma tarefa do ClickUp?

- **Propósito:** As alterações cumprem os requisitos (o DoD) da tarefa?

- **Funcionalidade:** O código foi testado? Ele funciona como deveria? (⚠️ Lembre-se: **ler é diferente de executar!**)

> ⚠️ **A Regra de Ouro da Entrega:** O trabalho só está verdadeiramente "concluído" quando o código passa por esse processo. Por isso, **uma tarefa no ClickUp só pode ser finalizada depois que o PR associado a ela for aprovado e integrado na branch develop.**
	
> 📒 **Conteúdos extras:** [Code Review](https://github.com/thoughtbot/guides/tree/main/code-review)
	
Assim que o revisor fizer a revisão, teremos três caminhos possíveis:

- **PR Aprovado ✅:** O PR pode ser mergeado na branch destino. Avise no Slack sobre a aprovação e o merge.

- **Alterações Solicitadas 🚧:** O revisor solicitou mudanças. Verifique os comentários, realize os ajustes e peça uma nova revisão. Avise no Slack sobre a solicitação de alterações e quaisquer dúvidas sobre as mudanças.

- **PR Reprovado ❌:** O PR foi reprovado. O revisor deve comunicar claramente o motivo e os próximos passos.

## GitFlow da Cognitivo

Agora que entendemos as peças, vamos ver como elas se movem juntas. Nosso fluxo de trabalho busca sempre garantir que tenhamos um ritmo que garante agilidade e segurança, além de garantir a previsibilidade das entregas.

* **Passo 1:** O Ponto de Partida (`develop`)

Tudo começa na `develop`. Pense nela como a nossa oficina principal. Antes de começar a martelar, garanta que você tem a planta mais recente do projeto.

```bash
git checkout develop
git pull
```

* **Passo 2:** Sua Bancada de Trabalho (`feature/` ou `fix/`)

Agora, crie seu espaço. Sua branch é sua bancada de trabalho, isolada e segura para você construir sem interferir no trabalho dos outros.

```bash
git checkout -b feature/minha-nova-feature
```

* **Passo 3:** A Construção (Commits Constantes)

Aqui entra a nossa filosofia: **"commits pequenos e constantes"**. Cada commit é um tijolo bem assentado na sua construção. **Não espere a parede inteira ficar pronta para registrar o progresso.** Isso cria um histórico limpo e facilita a vida de todos.

> 💡 **Dica:** Todo fim do dia, faça um commit do que você trabalhou. Isso ajuda a manter o histórico atualizado e reduz a chance de conflitos.

Utilize sempre o **AI Docs** para ajudá-lo em suas mensagens e commits.

* **Passo 4:** O Convite para a Revisão (O PR para `develop`)

Terminou sua parte? Ótimo. Agora é hora de chamar o mestre de obras para validar. Seu Pull Request para a `develop` é esse convite. **Preencha o template, explique sua obra e chame os revisores.**

* **Passo 5:** A Integração (merge na `develop`)

Com o feedback aplicado e o "ok" do revisor, seu trabalho se junta ao dos outros na oficina. A `develop` agora contém a sua contribuição, pronta para ser testada em conjunto com as outras novidades.

* **Passo 6:** O Lançamento (merge na `main`)

Este é o grande momento, gerenciado pelo Tech Lead. Quando um conjunto de funcionalidades na `develop` está sólido e validado, ele é promovido para a `main`. É como inaugurar o prédio. O código agora está em produção, servindo aos nossos clientes.

### ✅ Checklist Diário

Lembre-se sempre do checklist cotidiano:

!!! note "Checklist Diário"
    - [ ] 📅 **Always sync:** `git pull origin develop`
    - [ ] 🌱 **Branch naming:** `feature/` ou `fix/` + nome descritivo  
    - [ ] 📝 **Commit format:** `tipo(escopo): descrição`
    - [ ] 🔄 **PR template:** Preenchido completamente
    - [ ] 👤 **ClickUp link:** Conectado no PR


## **Boas Práticas: O Jeito Cognitivo de Usar Git**

Agora que você domina o fluxo, vamos falar sobre as práticas que **separam o profissional do amador**. Essas não são apenas recomendações; são os hábitos que tornam o nosso trabalho previsível, confiável e, acima de tudo, colaborativo.

**1. O Ritmo da Construção: Commits Pequenos e Constantes**

Pense nos commits como fotografias do progresso da sua obra. **Você não tira uma foto apenas quando a casa está pronta**, certo? Cada etapa importante merece ser registrada.

**Por que isso importa?**

- **Segurança:** Você nunca perde mais do que algumas horas de trabalho.

- **Clareza:** É mais fácil entender o que mudou entre duas fotos próximas.

- **Colaboração:** Conflitos são menores e mais fáceis de resolver.

**Na prática:**

- Terminou uma função? Commit.

- Corrigiu um bug específico? Commit.

- Adicionou um teste? Commit.

> 💡 **Regra de ouro:** Se você consegue explicar o commit em uma frase clara, ele tem o tamanho certo.

**2. Conflitos: Quando Duas Histórias se Encontram**

Conflitos não são problemas; **são conversas entre diferentes linhas de pensamento.** Quando o Git não consegue decidir qual versão manter, ele está pedindo para você ser o mediador dessa conversa.

**O processo de resolução:**

**Passo 1:** Entenda o cenário
```bash
git status
```

**Passo 2:** Abra os arquivos em conflito e seja o tradutor
- Analise as duas versões
- Entenda o que cada desenvolvedor estava tentando fazer
- Combine o melhor dos dois mundos (ou escolha a versão mais adequada)

**Passo 3:** Finalize a conversa
```bash
git add <arquivo-resolvido>
git merge --continue
```

> ⚠️ **Atenção:** Sempre teste o código após resolver conflitos. **Duas funcionalidades que funcionam separadamente podem não funcionar juntas.**

**3. O Hábito da Atualização**

**Começar o dia sincronizado é como alinhar os ponteiros do relógio.** Evita que você trabalhe em uma versão desatualizada e reduza conflitos desnecessários.

**Ritual diário:**
```bash
git checkout develop
git pull                     # Sincroniza com o servidor
git checkout feature/minha-branch
git merge develop            # Traz as novidades para sua branch
```

> 🎯 **Dica:** Faça isso **antes** de começar a codificar e **sempre** que voltar de uma pausa longa.

Essas práticas não são burocracias. **São os fundamentos que nos permitem trabalhar como uma orquestra**, onde cada músico sabe exatamente quando e como tocar sua parte.

## **Referência Rápida: Comandos Essenciais do Git**

Esta seção é o seu "canivete suíço" para o dia a dia. São os comandos que sustentam nosso fluxo de trabalho e te ajudam a manter o ritmo sem perder o controle.

**1. Rotina Diária (O Básico para o Dia a Dia)**

Comandos para o ciclo de trabalho principal: criar, salvar e sincronizar.

| Comando | Descrição |
|---|---|
| `git status` | Mostra o status das suas alterações: o que foi modificado, o que está pronto para commit e o que não está sendo rastreado. **Use antes de qualquer `commit` para ter certeza do que está enviando.** |
| `git add .` | Prepara **todas** as alterações nos arquivos modificados para serem incluídas no próximo commit. |
| `git add <arquivo>` | Prepara um arquivo específico para o próximo commit. Ideal para criar commits pequenos e lógicos. |
| `git commit -m "feat: msg"` | Cria um "snapshot" (uma foto) das suas alterações preparadas, com uma mensagem semântica. **É o Passo 3 do nosso GitFlow.** |
| `git pull` | Busca as atualizações do repositório remoto e as mescla na sua branch atual. **Use no Passo 1 do nosso GitFlow, na branch `develop`.** |
| `git push` | Envia seus commits locais para o repositório remoto, tornando-os visíveis para a equipe. |

**2. Analisando o Passado (Inspecionando o Histórico)**

Comandos para entender o que já foi feito e o que você está prestes a fazer.

| Comando | Descrição |
|---|---|
| `git log` | Exibe o histórico de commits da branch, mostrando autor, data e mensagem de cada um. |
| `git log --oneline --graph` | Mostra o histórico de forma compacta e visual, com uma linha por commit e um gráfico das ramificações (branches). **Muito útil para entender a linha do tempo.** |
| `git diff` | Mostra as diferenças detalhadas entre o que você modificou e o último commit. **Use para revisar suas próprias alterações antes de um `git add`.** |
| `git diff --staged` | Mostra as diferenças do que já foi preparado (`staged`) com `git add` em relação ao último commit. |

**3. Navegando e Criando (Trabalhando com Branches)**

Comandos para gerenciar suas linhas de trabalho.

| Comando | Descrição |
|---|---|
| `git branch` | Lista todas as branches locais e indica em qual você está. |
| `git checkout <nome-da-branch>` | Muda para uma branch já existente. |
| `git checkout -b feature/nome` | Cria uma nova branch a partir da atual e já muda para ela. **É o Passo 2 do nosso GitFlow.** |
| `git merge develop` | Traz as atualizações da branch `develop` para a sua branch atual. **Essencial para manter seu trabalho sincronizado.** |

**4. Corrigindo o Percurso (Desfazendo e Salvando Alterações)**

Comandos para situações inesperadas. Use com atenção!

| Comando | Descrição |
|---|---|
| `git stash` | Guarda suas alterações não commitadas "na gaveta" temporariamente, limpando sua área de trabalho. Útil quando você precisa mudar de branch rapidamente sem commitar. |
| `git stash pop` | Traz de volta as últimas alterações que você guardou com `git stash`. |
| `git restore <arquivo>` | ⚠️ **Cuidado!** Descarta as alterações em um arquivo que **ainda não foi preparado** (`staged`), restaurando-o para a versão do último commit. |
| `git reset --hard HEAD~1` | ☠️ **MUITO CUIDADO!** Apaga completamente o último commit local. **Use apenas se tiver certeza absoluta e NUNCA se o commit já foi enviado com `git push`.** |