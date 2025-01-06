# O git 😁

* **Por que usar Git?**

O Git é uma ferramenta essencial para o desenvolvimento de software moderno, oferecendo controle de versão distribuído. Ele permite que equipes colaborem de forma eficiente, mantendo o histórico das alterações e garantindo que o código esteja sempre organizado. Algumas vantagens principais incluem:

- **Histórico de Alterações:** Permite rastrear todas as mudanças feitas no código ao longo do tempo.

- **Colaboração:** Suporta trabalho em equipe com branchs e merges, permitindo que múltiplos desenvolvedores trabalhem simultaneamente.

- **Segurança:** O armazenamento distribuído garante que os dados estejam sempre seguros.

- **Flexibilidade:** Adapta-se a diferentes fluxos de trabalho e tamanhos de equipe.

## Padronização de Commits

A padronização dos commits tem como objetivo trazer um histórico mais detalhado para o projeto, onde podemos ver “de cara” as mudanças que foram implementadas com aquele commit e atualizações do repositório. Um commit deve ser feito sempre que fazemos alguma alteração no código, como uma feature, fix, docs e etc. A granularidade dos commits podem variar, dessa forma, devemos sempre fazer o commit quando terminamos de fazer determinada tarefa, como corrigir um bug, implementar uma feature, criar a documentação, ajustar o estilo do código, etc. E, para facilitar o entendimento do que cada commit representa, devemos seguir o padrão de commits semânticos, para garantir que conseguimos entender diretamente o que foi feito.

Para isso, podemos seguir o seguinte padrão:

```plaintext
<tipo>(escopo opcional): <descrição>
```

Onde cada estrutura tem uma função específica:

- **type:** indica o tipo do commit. Podemos ter alguns tipos, que podem variar, mas ambos devem seguir o mesmo padrão e devem ser sucintos ao indicar o tipo do commit. Alguns exemplos são:
    
    - **feat:** identifica um novo recurso
    - **fix:** correção de um bug
    - **chore:** alterações que não estão relacionadas a uma correção ou recurso e não modificam arquivos src ou de teste (por exemplo, atualização de dependências)
    - **refactor:** código refatorado que não corrige um bug nem adiciona um recurso
    - **docs:** atualizações na documentação, como o README ou outros arquivos markdown
    - **style:** alterações que não afetam o significado do código, provavelmente relacionadas à formatação do código, como espaço em branco, falta de ponto e vírgula e assim por diante.
    - **test:** incluindo testes novos ou corrigindo testes anteriores
    - **perf:** melhoria na performance do código
    - **ci:** integração contínua relacionada
    - **build:** mudanças que afetam o sistema de compilação ou dependências externas
    - **revert:** reverte um commit anterior

- **scope:** Escopo onde foi feito o commit, ou seja, onde foi feita a alteração. Pode ser um componente, uma página, um módulo, etc. Esse campo é opcional, mas é interessante para facilitar a busca de commits relacionados a um determinado escopo.

- **description:** Aqui deve-se trazer a descrição da alteração que foi feita. Essa descrição deve ser feita sucintamente, buscando ser direto ao ponto e explicar bem o que foi feito. Evitar descrições muito vagas, onde não se tem ideia do que foi feito. Também podemos adicionar aqui o link da tarefa do ClickUp referente ao commit.

### Exemplos:

* **Bons:** ✅

    - `feat: melhora do desempenho com o carregamento lento das imagens`

    - `feat(auth): implementa autenticação JWT`

    - `fix: correção do treinamento do modelo, fazendo o fit na porção correta do treinamento`

    - `chore: inserção de dependência faltando - scikit-learn`

    - `docs: atualização do README com instruções de instalação`

    - `fix(api): corrige erro no endpoint de usuários`

    - `style: aplicação de formatador de código black`

- **Ruins:** ❌

    - `agora vai!`

    - `<vazio>`

    - `correção de um erro`

    - `commit 2`


## Trabalhando com Branches


Branches são uma parte fundamental do Git, permitindo que você trabalhe em diferentes versões do seu código ao mesmo tempo. Eles são úteis para isolar o trabalho em progresso, testar novas funcionalidades e colaborar com outros desenvolvedores.

Beleza, todos os repositórios possuem branches, mas quando eu devo abrir uma branch ou como eu devo abrir uma branch?

> Sempre que você for trabalhar em uma nova funcionalidade, correção de bug ou qualquer outra tarefa, você deve abrir uma branch para isso. Isso ajuda a manter o código organizado e facilita a revisão de código.

Nos repositórios do projeto, temos algumas convenções para nomear as branches:

- **`main`** ou **`master`:** Versão estável, pronta para produção.
- **`develop`:** Branch principal para desenvolvimento.
- **`feature/<nome>`:** Para novas funcionalidades.
- **`hotfix/<nome>`:** Correções críticas em produção.
- **`bugfix/<nome>`:** Correção de bugs detectados no ambiente de testes.

Exemplos:

- `feature/melhorias-performance`
- `hotfix/corrige-login`
- `bugfix/ajuste-tamanho-imagem`

## Merges e Pull Requests

Quando você terminar de trabalhar em uma branch, você deve criar um Pull Request (PR) para mesclar suas alterações de volta para a branch principal. Isso permite que outros desenvolvedores revisem seu código e forneçam feedback antes de mesclar as alterações.

Para garantir que nosso PR seja revisado e mesclado com sucesso, devemos seguir algumas boas práticas:

- **Tamanho dos PRs:** os PRs deve ser sucintos e diretos ao ponto, PRs muitos grandes podem ser demorados para serem revisados

- **Título e Descrição:** um PR bem descrito e detalhado leva a um review mais objetivo e rápido. Busque sempre elaborar um título auto explicativo que descreva o que o PR faz. **Na descrição, sempre detalhe o que foi alterado, por que foi alterado e como foi alterado.**
    
    - Use prints, se necessário, para detalhar as modificações.
    
    - Aqui devemos também sempre adicionar o card do ClickUp, quando possível referenciar, para conseguirmos linkar a tarefa relacionada com a entrega.

- **Os PRs sempre devem ser feitos para uma branch abaixo da main/master, como a develop, homolog ou outra branch de testes antes de subir para a main/master**

- Sempre que abrirmos um PR devemos avisar, no Slack, o Project Lead e o Tech Lead do projeto, bem como os revisores responsáveis. De preferência, mande no canal do projeto.

- Fique ligado:
    - [The anatomy of a perfect pull request | by Hugo Dias](https://hugooodias.medium.com/the-anatomy-of-a-perfect-pull-request-567382bb6067)


## Reviews

A arte de revisar é importante, todo PR deve ser revisado antes de ser mesclado na branch destino. Desta forma, devemos sempre marcar alguém como revisor. No contexto dos projetos, sempre que tivermos a figura do Tech Lead, ele deve ser a pessoa que irá revisar, ou, em caso de dúvida, sempre pergunte ao PL, ele saberá indicar quem deverá ser marcado como revisor. 
	
> Caso não exista alguém para revisar no momento, isso deve ser apontado no PR! Trazendo como comentário ou ponto adicional para deixar claro que não existia alguém para revisar no momento.
	
📒 Fique ligado: [Code Review](https://github.com/thoughtbot/guides/tree/main/code-review)
	
Assim que o revisor fizer a revisão, teremos três caminhos possíveis:

- **PR Aprovado ✅:** pode-se seguir o fluxo e realizar o merge na branch principal, fechando, dessa forma, o PR. Sendo feito o merge, devemos avisar no Slack que o merge foi feito e as alterações já foram realizadas. Se você for o revisor, sempre avise que aprovou o PR no canal do Slack.

- **Alterações Solicitadas 🚧:** o revisor detectou que existem alterações a serem realizadas, dessa forma devemos ver os comentários deixados pelo revisor no PR (se você for o revisor, sempre avise que solicitou alterações no canal do Slack). Após realizar as alterações, devemos solicitar ao revisor que olhe se está tudo ok, ele dando o aceite, podemos seguir para o merge e o processo corre como no tópico anterior.

- **PR Reprovado ❌:** Neste caso o seu PR, por algum motivo que deve ser esclarecido pelo revisor, foi reprovado. Caso você seja o revisor, sempre comunique o motivo que levou a ser recusado e o que deve-se ser feito para os próximos passos.

## Boas Práticas com Git

### 1. **Commits Frequentes e Pequenos**
Realize commits com frequência para evitar perda de trabalho e facilitar revisões.

### 2. **Evite Commits Ambíguos**
Sempre use mensagens descritivas e específicas. Evite commits como "agora vai" ou "pequenos ajustes".

### 3. **Resolvendo Conflitos**
Conflitos podem surgir ao trabalhar em equipes. Resolva-os seguindo este fluxo:

- Identifique os arquivos em conflito:

```bash
git status
```

- Abra os arquivos em conflito e resolva as diferenças manualmente.

- Adicione os arquivos resolvidos:

```bash
git add <arquivo>
```

- Continue com o merge:

```bash
git merge --continue
```

### 4. **Automatização**

Use ferramentas como `pre-commit hooks` para automatizar validações, como linting e formatação.


## Comandos Úteis do Git

| Comando                          | Descrição                                   |
|----------------------------------|-------------------------------------------|
| `git status`                     | Verifica o estado atual do repositório.   |
| `git log`                        | Exibe o histórico de commits.             |
| `git diff`                       | Mostra diferenças entre versões.          |
| `git stash`                      | Salva mudanças temporariamente.           |
| `git reset --hard <commit>`      | Restaura o repositório para um commit específico. |
| `git rebase -i <branch>`         | Reorganiza commits para uma branch.       |

