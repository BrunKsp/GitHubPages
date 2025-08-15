# 🌐 Projeto Exemplo – GitHub Pages + GitHub Actions

Este repositório foi criado para **ensinar Git, GitHub e GitHub Actions** de forma prática e simples para os alunos da ***Antonio Meneghetti Faculdade***, publicando um site estático no **GitHub Pages**.
---
![Imagem da aula](./public/assets/image.jpg)

## 📚 Objetivo da Aula

- Entender o que é **Git** e como versionar código.
- Aprender a usar **GitHub** para hospedar projetos.
- Criar e configurar um **GitHub Pages**.
- Automatizar publicação com **GitHub Actions**.

---

## 🛠 Tecnologias e Conceitos

- **Git** – Controle de versão.
- **GitHub** – Hospedagem de código e colaboração.
- **GitHub Pages** – Publicação de sites estáticos.
- **GitHub Actions** – Automação de processos (CI/CD).
- **YAML** – Formato de configuração de workflows.

---

## 🚀 Passo a Passo da Aula

### 1️⃣ Clonar o Repositório
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

---

### 2️⃣ Criar ou Editar o Site

O arquivo principal do site será o **`index.html`**.  
Edite ou crie este arquivo com o conteúdo desejado.

Após editar, salve e envie para o repositório:

```bash
git add index.html
git commit -m "Criando site inicial"
git push origin main
```

---

### 3️⃣ Configurar o GitHub Pages

1. No repositório, vá em **Settings** (Configurações).
2. No menu lateral, clique em **Pages**.
3. Em **Source**, selecione:
   - **Branch:** `main`
   - **Folder:** `/ (root)`
4. Clique em **Save**.
5. O GitHub exibirá o **link do seu site** no topo da página.

💡 Exemplo de link gerado:
```
https://seu-usuario.github.io/seu-repositorio/
```

---

## ⚙️ Workflow do GitHub Actions

O workflow abaixo automatiza a publicação do site no GitHub Pages sempre que houver um **push** na branch `main`.

```yaml
name: Deploy no GitHub Pages

on:
  push:
    branches: [ "main" ]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Baixar código
        uses: actions/checkout@v4

      - name: Publicar no GitHub Pages
        uses: peaceiris/actions-gh-pages@v4
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: .
```

---

## 📂 Estrutura do Projeto
```
📦 meu-projeto
 ┣ 📜 index.html
 ┣ 📜 style.css
 ┗ 📂 .github
    ┗ 📂 workflows
       ┗ 📜 deploy.yml
```

---

## 💡 Explicando o CI/CD na Prática

- **CI (Integração Contínua):** cada alteração enviada é validada.
- **CD (Entrega Contínua):** o site é publicado automaticamente no GitHub Pages.

Fluxo:
```
Commit → Push → GitHub Actions → Deploy no Pages → Site Online
```

---

## 🔗 Link do Site

Depois que o Pages for configurado, seu site estará disponível em:
```
https://seu-usuario.github.io/seu-repositorio/
```

---

## 📖 Conteúdo Extra para a Aula

- Criar branches e abrir **Pull Requests**.
- Adicionar colaboradores ao repositório.
- Personalizar o workflow com testes automatizados antes do deploy.
