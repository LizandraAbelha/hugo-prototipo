---
title: "O Nosso Guia Completo do Hugo"
date: 2025-11-10T22:15:00-03:00
draft: false
layout: "single"
---

Bem-vindo ao nosso projeto! Este site foi inteiramente construído com **Hugo**, e esta página serve como um guia prático sobre como o fizemos e como a ferramenta funciona.

---

## 1. O que é o Hugo?

O Hugo é um **Gerador de Sites Estáticos (SSG)** de código aberto, escrito na linguagem Go.

Diferente de sistemas como o WordPress, que precisam de um banco de dados e processamento no servidor a cada visita, o Hugo "constrói" o site **uma única vez**. Ele pega os seus ficheiros de conteúdo (Markdown) e os seus templates (HTML) e gera um site 100% estático (HTML, CSS e JavaScript puros).

**As principais vantagens são:**
* **Velocidade:** Sites estáticos carregam quase instantaneamente. O nosso objetivo é < 3 segundos, o que é fácil com o Hugo.
* **Segurança:** Sem banco de dados ou processamento de servidor, não há nada para "hackear".
* **Simplicidade:** O desenvolvimento é todo feito em ficheiros de texto, o que é perfeito para versionamento com Git.

O Hugo foi criado em 2013 por Steve Francia e é hoje mantido por Bjørn Erik Pedersen e uma grande comunidade.

---

## 2. A Arquitetura do Hugo: Como Funciona?

O Hugo funciona através de uma estrutura de pastas muito lógica. Para construir este site, nós focámo-nos nestas pastas principais:

* **`content/`**
  É o "O Quê". É onde todo o nosso conteúdo vive. As páginas da **Lizandra, Bruna e Gabriel** estão em `content/equipe/`. Esta própria página está em `content/_index.md`. Escrevemos tudo em **Markdown**, uma linguagem de formatação simples.

* **`layouts/`**
  É o "Como". Esta pasta define a aparência (o HTML) do conteúdo. No entanto, para acelerar o desenvolvimento, nós não criámos os nossos layouts do zero.

* **`themes/`**
  Em vez de usar a pasta `layouts/`, nós instalámos um tema pré-feito (o **PaperMod**) dentro desta pasta. Um tema é apenas um conjunto de layouts e estilos (CSS) que outra pessoa já criou. O nosso trabalho de front-end foi *customizar* este tema.

* **`static/`**
  É onde colocamos todos os nossos "assets" estáticos. As nossas fotos de perfil (ex: `lizandra-perfil.jpg`), logotipos, ou ficheiros CSS personalizados vivem aqui.

* **`hugo.toml`**
  É o "cérebro" do site. É o ficheiro de configuração principal. É aqui que definimos o título do site (`title`), o tema que estamos a usar (`theme = "PaperMod"`), e configuramos os nossos menus.

---

## 3. Principais Comandos do Hugo

Para este projeto, alguns comandos foram essenciais no nosso dia a dia:

```bash
# 1. Iniciar o servidor de desenvolvimento
# O '-D' força a exibição de 'drafts' (rascunhos)
hugo server -D

# 2. Criar uma nova página de conteúdo
# Este comando cria o ficheiro .md com o 'front matter' básico
hugo new equipe/lizandra.md

# 3. Instalar um tema (como fizemos com o PaperMod)
# Isto usa 'Git Submodules' para linkar o tema ao nosso projeto
git submodule add [URL_DO_TEMA] themes/[NOME_DO_TEMA]

# 4. Construir o site final
# Este é o comando que o GitLab CI/CD roda. 
# Ele gera a pasta 'public/' com o site pronto.
hugo
```

4. Como Este Site Foi Gerido
Este projeto não foi só sobre código; foi sobre gestão. Usámos as ferramentas do GitLab para organizar o nosso trabalho de 15 semanas:

Gestor (Gabriel): Definiu o escopo e criou todas as tarefas (ex: "Criar página de perfil", "Configurar CI/CD") como GitLab Issues. Ele organizou estas tarefas num GitLab Board (Kanban) para sabermos o que estava "A Fazer", "Fazendo" e "Concluído".

Back-end/DevOps (Bruna): Focou-se na automação. Ela escreveu o ficheiro .gitlab-ci.yml que permite a Integração e Deploy Contínuos (CI/CD). Graças ao seu trabalho, sempre que enviamos código (git push) para o GitLab, o Hugo constrói o site e publica-o no GitLab Pages automaticamente.

Front-End (Lizandra): Focou-se na experiência do utilizador. Ela pesquisou e instalou o tema PaperMod, configurou o hugo.toml (menus, modo dark/light) e criou a estrutura de conteúdo (perfis, guia) que você está a ler agora, garantindo os requisitos de acessibilidade e performance.

