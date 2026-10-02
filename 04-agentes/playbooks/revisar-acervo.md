# Playbook: revisão periódica

Executar a pedido do usuário (sugerido: semanal).

1. Processar o inbox (`processar-inbox.md`).
2. Verificar a estrutura de `02-workspace/`: notas soltas na raiz, pastas quase duplicadas, pastas com mais de 10 notas ou com mais de 3 níveis. Reorganizar conforme "Organização do workspace" do `AGENTS.md`.
3. Verificar o frontmatter das notas do workspace: campos do template ausentes, nota sem `tema`, nota sem links, nota derivada sem `origem`. Corrigir.
4. Duplicatas ou notas sobrepostas: consolidar em uma, marcando a outra como `status: obsoleto` com link para a nota que a substituiu.
5. Entradas do `index.md` com links quebrados ou notas importantes ausentes: corrigir.
6. Projetos com `status: ativo` cuja nota não é atualizada há mais de 30 dias: listar para o usuário.
7. Ler `aprendizados.md` e `pendencias.md`: propor ao usuário novas regras ou playbooks e resolver pendências.
8. Registrar a revisão em `log.md` com uma linha, mencionando só o que mudou de relevante (consolidações, reorganizações, pendências levantadas).
