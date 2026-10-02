# AGENTS.md

Este repositório é um cofre do Obsidian que funciona como a memória de longo prazo do usuário ("segundo cérebro"). Todo conhecimento importante é guardado aqui. Escreva em pt-br, em Markdown, com `[[wikilinks]]`.

## Antes de agir

1. Leia `index.md` (mapa do acervo) e `04-agentes/aprendizados.md` (correções e preferências anteriores).
2. **Ao criar ou editar qualquer arquivo `.md`, leia e siga a skill `.agents/skills/obsidian-markdown/SKILL.md`** (e as referências em `.agents/skills/obsidian-markdown/references/` quando precisar de propriedades, callouts ou embeds). Ela define a sintaxe Obsidian válida: wikilinks, propriedades (frontmatter), tags, callouts e embeds. Em conflito, as regras deste arquivo sobre estrutura, templates e pastas prevalecem; a skill governa só a sintaxe.
3. Consulte o playbook correspondente em `04-agentes/playbooks/`:
   - `processar-inbox.md`: organizar o que está em `00-inbox/`.
   - `consultar-acervo.md`: responder perguntas usando o acervo.
   - `revisar-acervo.md`: manutenção periódica.

## Estrutura

| Pasta | Função | Agente pode editar? |
|---|---|---|
| `00-inbox/` | Captura ainda não processada | Sim (processar e esvaziar) |
| `01-conhecimento/` | Conteúdo produzido pelo usuário. Fonte de verdade | **Somente adicionar** (arquivos novos vindos do inbox). Nunca editar, renomear, mover ou apagar o existente |
| `02-workspace/` | Única área de trabalho dos agentes: notas derivadas, sínteses, rascunhos, análises, projetos, pessoas e diário (ver "Organização do workspace") | Sim, exceto `diario/` (só acrescentar) |
| `03-referencias/` | Material original de terceiros (artigos, PDFs, transcrições) | **Somente adicionar.** Nunca editar, renomear, mover ou apagar o existente |
| `04-agentes/` | `templates/`, `playbooks/`, `aprendizados.md`, `pendencias.md` | Sim (templates e playbooks existentes só com aprovação) |

Na raiz: `index.md` (mapa do acervo, agrupado por tema) e `log.md` (registro append-only de eventos importantes, ver "Registro" em Regras).

### Organização do workspace

`02-workspace/` deve ter sempre uma estrutura de pastas clara. Nenhuma nota fica solta na raiz dele. Pastas são criadas **sob demanda**: não precisam existir antes de serem usadas.

**Onde colocar uma nota** (use a primeira regra que se aplicar):

1. Pertence a um projeto (algo com objetivo e fim) → `projetos/<Projeto>/`. Cada projeto tem uma subpasta com a nota do projeto (template `projeto`, nome igual ao da pasta) e as notas derivadas dele.
2. É sobre uma pessoa → `pessoas/<Nome>.md` (template `pessoa`, uma nota por pessoa).
3. É um registro datado do dia a dia → `diario/YYYY-MM-DD.md` (template `diario`). Só acrescentar; nunca reescrever o passado.
4. Qualquer outro caso → `<assunto>/`, uma pasta com nome descritivo em pt-br (ex.: `finanças/`). Não use nomes genéricos (`outros/`, `diversos/`).

**Pastas e temas são coisas diferentes.** A pasta organiza o arquivo no disco (regras acima). O `tema` (frontmatter) classifica o conteúdo e agrupa o `index.md`. Uma nota em `projetos/Casa/` pode ter `tema: finanças`.

**Manutenção da estrutura**

- Antes de criar nota ou pasta, liste `02-workspace/` e consulte o `index.md`. Reutilize a pasta adequada; não crie pastas quase iguais (ex.: `financas/` e `finanças/`).
- Quando uma pasta tiver mais de 10 notas, agrupe-as em subpastas por assunto. Profundidade máxima: 3 níveis de pasta abaixo de `02-workspace/`.
- Criar pasta, mover ou renomear nota no workspace é permitido. Ao fazer isso, atualize os wikilinks afetados e o `index.md`. Registre no `log.md` (ação `criou` ou `moveu`, com o caminho) só reorganizações relevantes, como criar uma pasta nova ou mover várias notas.

## Regras

- **`01-conhecimento/` e `03-referencias/` são protegidas.** Não há trava técnica: a regra depende de você respeitá-la. Interpretações, resumos e sugestões de mudança vão em `02-workspace/`. Se algo protegido precisar ser corrigido ou substituído, pergunte ao usuário. O usuário pode promover uma nota do workspace para `01-conhecimento/`.
- **Sintaxe Obsidian**: toda criação ou edição de `.md` segue a skill `obsidian-markdown` (ver "Antes de agir").
- **Wikilinks**: use `[[wikilinks]]` para notas do cofre e links Markdown só para URLs externas. Linke pelo nome da nota (`[[Nome]]`); use o caminho (`[[pasta/Nome]]`) só quando existirem duas notas com o mesmo nome.
- **Frontmatter**: obrigatório em todas as notas criadas por agentes, copiado do template correspondente em `04-agentes/templates/`. Campos comuns a todos os templates: `tipo`, `criado`, `atualizado`, `tema`, `tags`. Cada template pode ter campos próprios (ex.: `status`, `autoria`, `origem`); preencha todos. `origem` é obrigatório em notas derivadas de outro arquivo do cofre. Atualize `atualizado` a cada edição, inclusive ao acrescentar no diário. Arquivos do usuário e referências não precisam de frontmatter.
- **Buscar antes de criar.** Comece pelo `index.md`, depois busque por título e tags. Atualize a nota existente do workspace em vez de duplicar.
- **Notas atômicas**: uma ideia por arquivo, título descritivo em pt-br (nome do arquivo = título), ligada a pelo menos outra nota.
- **Tema** (ex.: trabalho, família, finanças) é um valor livre no frontmatter. Reutilize os temas já existentes no `index.md` antes de criar outro; um tema novo ganha uma seção `## tema` no `index.md`.
- **Rastreabilidade**: conhecimento derivado aponta a fonte em `origem`. Distinga fato da fonte, inferência do agente e opinião do usuário. Quando `01-conhecimento/` e `02-workspace/` divergirem, vale o `01-conhecimento/`.
- **Nada é apagado**: o que ficar obsoleto ganha `status: obsoleto` (válido em qualquer template) e um link para o substituto.
- **Registro**: o `log.md` guarda só o que for importante e útil para o futuro (ex.: decisão de estrutura, consolidação de notas, mudança de rumo de um projeto, processamento do inbox em lote). Não registre rotina (criar ou editar uma nota comum, corrigir link, ajustar formatação): isso já está no histórico do git. Na dúvida, pergunte-se "alguém vai precisar disso daqui a meses?"; se não, não registre. Notas-chave entram no `index.md`.
- **Privacidade**: o conteúdo pode ser pessoal e sensível (finanças, saúde, família). Não o envie a serviços externos nem o cite fora do cofre sem pedido do usuário.
- **Git**: não faça commit sem pedido do usuário.

## Como os agentes evoluem

- Correções e preferências do usuário vão para `04-agentes/aprendizados.md`.
- Dúvidas para confirmar vão para `04-agentes/pendencias.md`.
- Procedimentos recorrentes viram playbooks em `04-agentes/playbooks/`.
- Mudanças neste `AGENTS.md` só com aprovação do usuário: proponha, não aplique.
