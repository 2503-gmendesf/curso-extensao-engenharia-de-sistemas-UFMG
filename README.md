# 🎓 Site do Curso — Jekyll Chirpy Theme

Site estilo GitHub Pages para divulgação de curso de atualização/extensão universitária, baseado no tema [Jekyll Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy).

---

## 📁 Estrutura do Projeto

```
curso-site/
├── _config.yml              # Configurações principais do site
├── _data/
│   ├── contact.yml          # Links de contato (sidebar)
│   └── share.yml            # Botões de compartilhamento
├── _posts/                  # Posts/páginas do site
│   ├── 2026-04-01-apresentacao.md
│   ├── 2026-04-02-ementa.md
│   ├── 2026-04-03-docentes.md
│   ├── 2026-04-04-certificacao.md
│   ├── 2026-04-05-faq.md
│   └── 2026-04-06-inscricoes.md
├── _tabs/                   # Abas do menu lateral
│   ├── about.md
│   ├── archives.md
│   ├── categories.md
│   └── tags.md
├── assets/
│   └── img/
│       └── logo.png         # ⚠️ Substitua pelo logo do seu curso
├── .github/
│   └── workflows/
│       └── pages-deploy.yml # CI/CD automático para GitHub Pages
├── index.html               # Página inicial
├── Gemfile                  # Dependências Ruby
└── .gitignore
```

---

## 🚀 Como Usar

### 1. Pré-requisitos

- [Ruby](https://www.ruby-lang.org/) >= 3.1
- [Bundler](https://bundler.io/)
- [Git](https://git-scm.com/)

### 2. Clone e instale as dependências

```bash
git clone https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git
cd SEU_REPOSITORIO
bundle install
```

### 3. Rode localmente

```bash
bundle exec jekyll serve
```

Acesse em: **http://localhost:4000**

---

## ⚙️ Configuração Inicial (`_config.yml`)

Edite o arquivo `_config.yml` e substitua os campos marcados com `[ ]`:

```yaml
title: MeuCurso                          # Nome do curso/site
tagline: Subtítulo do curso              # Subtítulo que aparece no sidebar
description: Descrição para SEO          # Descrição resumida
url: "https://seunome.github.io"         # URL do seu GitHub Pages
baseurl: ""                              # Deixe vazio se for repositório principal

github:
  username: seunome                      # Seu usuário GitHub

social:
  name: Nome do Organizador
  email: contato@email.com

avatar: /assets/img/logo.png             # Logo do curso
theme_mode: dark                         # dark ou light
```

---

## 📝 Personalizando os Posts

Os posts ficam em `_posts/` e seguem o padrão de nomenclatura:

```
YYYY-MM-DD-nome-do-post.md
```

### Cabeçalho (Front Matter) de cada post

```yaml
---
title: "Título do Post"
date: 2026-04-01 08:00:00 -0300
categories: [Categoria]
tags: [tag1, tag2]
pin: true        # fixa o post no topo (opcional)
toc: true        # exibe sumário lateral (opcional)
---
```

### Posts incluídos

| Arquivo | Conteúdo | Personalizar |
|---|---|---|
| `2026-04-01-apresentacao.md` | Página inicial do curso | Datas, descrição geral |
| `2026-04-02-ementa.md` | Ementa com módulos e tópicos | Módulos, carga horária |
| `2026-04-03-docentes.md` | Corpo docente | Nomes, bios, links |
| `2026-04-04-certificacao.md` | Regras de certificação | Notas, prazos, requisitos |
| `2026-04-05-faq.md` | Perguntas frequentes | Respostas específicas do seu curso |
| `2026-04-06-inscricoes.md` | Inscrições e bolsas | Datas, valores, link do formulário |

---

## 🖼️ Logo do Curso

Substitua o arquivo `assets/img/logo.png` pela imagem do logo do seu curso.

- **Formato recomendado:** PNG com fundo transparente
- **Tamanho:** 200×200px ou maior (quadrado)

---

## 🌐 Publicar no GitHub Pages

### Método 1 — GitHub Actions (recomendado)

O workflow `.github/workflows/pages-deploy.yml` já está configurado para build e deploy automático.

**Passos:**

1. Crie um repositório no GitHub (ex: `nome-do-curso`)
2. Faça push do projeto:
   ```bash
   git init
   git add .
   git commit -m "chore: initial site setup"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/nome-do-curso.git
   git push -u origin main
   ```
3. No repositório GitHub, acesse **Settings > Pages**
4. Em **Source**, selecione: **GitHub Actions**
5. Aguarde o workflow rodar (aba **Actions**)
6. Seu site estará em: `https://SEU_USUARIO.github.io/nome-do-curso`

### Método 2 — Branch `gh-pages`

Se preferir deploy manual:

```bash
bundle exec jekyll build
# O site gerado estará na pasta _site/
# Faça push da pasta _site/ para a branch gh-pages
```

---

## 📌 Dicas de Personalização

### Adicionar novo post

```bash
# Crie um arquivo em _posts/
touch _posts/2026-04-10-novo-post.md
```

### Mudar tema de cor (dark/light)

No `_config.yml`:
```yaml
theme_mode: light   # ou dark
```

### Adicionar aba no menu lateral

Crie um arquivo em `_tabs/`:

```markdown
---
title: Conteúdo
icon: fas fa-book
order: 5
---

Seu conteúdo aqui.
```

### Adicionar Google Analytics

No `_config.yml`:
```yaml
analytics:
  google:
    id: "G-XXXXXXXXXX"
```

### Fixar posts importantes

No cabeçalho do post:
```yaml
pin: true
```

---

## 🔗 Links Úteis

- [Documentação do Chirpy](https://chirpy.cotes.page/)
- [Guia de configuração do Chirpy](https://chirpy.cotes.page/posts/getting-started/)
- [GitHub Pages — Documentação oficial](https://docs.github.com/pt/pages)
- [Jekyll — Documentação oficial](https://jekyllrb.com/docs/)

---

## 📄 Licença

Este projeto usa o tema [jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) licenciado sob MIT.  
O conteúdo dos posts é de autoria dos organizadores do curso.
