---
title: "Sobre o Projeto"
date: 2025-11-10T22:45:00-03:00
draft: false
layout: "single"
---

Este site é o projeto final da disciplina de **Gestão de Projetos de Software**.

O nosso objetivo principal não era apenas construir um site, mas **gerir** o processo de desenvolvimento do início ao fim, aplicando na prática os conceitos aprendidos em aula, como metodologias ágeis e controlo de versão.

### Porquê Hugo?

Escolhemos **Hugo** como a principal ferramenta técnica. Sendo um gerador de sites estáticos (SSG), ele foi a escolha perfeita para cumprir os requisitos de qualidade do projeto:

* **Performance:** O Hugo gera HTML puro, o que nos permite atingir facilmente as metas de carregamento (< 3s) e pontuações altas no Google PageSpeed (> 90).
* **Segurança:** Sem banco de dados, a superfície de ataque é quase nula.
* **DevOps:** Integra-se perfeitamente com o fluxo de trabalho de CI/CD.

### A Nossa Gestão e Stack Tecnológica

Todo o projeto foi gerido usando o **GitLab**. O nosso fluxo de trabalho seguiu as melhores práticas de DevOps:

1. **Gestão (Kanban):** O Gabriel (Gestor) usou o **GitLab Issues** para criar todas as tarefas e o **GitLab Boards** para as organizar.
2. **Desenvolvimento (Git):** A Lizandra (Front-End) e a Bruna (Back-End) desenvolveram o site localmente, enviando o código para o GitLab (`git push`).
3. **CI/CD (Automação):** A Bruna configurou um pipeline (`.gitlab-ci.yml`) que "ouve" os pushes. A cada novo envio, o GitLab automaticamente:
    * Roda o comando `hugo` para construir o site estático.
    * Publica (faz o "deploy") da nova versão do site no GitLab Pages.