# Playbook: processar o inbox

1. Liste `00-inbox/` e leia cada item.
2. **Preserve o original.** Em caso de dúvida sobre a autoria, pergunte (registre em `pendencias.md` se o usuário não estiver disponível e deixe o item no inbox). Depois mova o item sem alterá-lo:
   - Produzido pelo usuário (inclui anotações do dia a dia e textos sobre projetos ou pessoas) → `01-conhecimento/`.
   - De terceiros → `03-referencias/`.
3. **Derive para o workspace.** Um item pode gerar várias notas. Para cada ideia durável, siga "Onde colocar uma nota" do `AGENTS.md`:
   - Registro do dia → acrescente em `02-workspace/diario/YYYY-MM-DD.md` (crie se não existir).
   - Sobre um projeto → atualize a nota do projeto em `02-workspace/projetos/<Projeto>/` (crie se não existir).
   - Sobre uma pessoa → atualize `02-workspace/pessoas/<Nome>.md` (crie se não existir).
   - Ideia atômica → nota no assunto adequado (template `nota`).
   - Busque antes e atualize notas existentes em vez de duplicar. Em toda nota derivada, `origem` aponta para o arquivo original já movido.
4. Preencha `tema` no frontmatter e ligue às notas relacionadas com `[[wikilinks]]`.
5. Atualize `index.md`. Registre em `log.md` uma única linha resumindo o lote, só se houver algo importante para o futuro (ex.: projeto ou pasta nova, decisão relevante); não registre cada nota.
6. O inbox deve terminar vazio, exceto itens pendentes de resposta do usuário.
