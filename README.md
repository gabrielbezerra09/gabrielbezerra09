# Opa! 👋

## Sobre mim

Meu nome é **Gabriel Bezerra**. Sou estudante de **Desenvolvimento Web, Design e Programação**.

📚 Atualmente, estou cursando o **1° ano** do **Curso Técnico em Informática para Internet** no **IFRN - Campus Natal-Central**.

🌍 Atualmente, eu falo Português e Inglês.

---

## Aprendendo
### Desenvolvimento Web
![HTML5](https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white&logoBackgroundColor=000000)
![CSS3](https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white&logoBackgroundColor=000000)

### Linguagens de programação
![Python](https://img.shields.io/badge/PYTHON-%2314354C.svg?style=for-the-badge&logo=python&logoColor=white)

### Ferramentas de Design
![Affinity](https://img.shields.io/badge/Affinity-90EE90?style=for-the-badge&logo=affinitydesigner&logoColor=white&logoBackgroundColor=000000)
![Figma](https://img.shields.io/badge/Figma-E6E6FA?style=for-the-badge&logo=figma&logoColor=orange&logoBackgroundColor=000000)
---

## ✉️ Contato

- Email: [gabrielbezerragomes80@gmail.com](mailto:gabrielbezerragomes80@gmail.com)
- Instagram: [@_g.bezerra11](http://instagram.com/_g.bezerra11)

name: Generate Pacman Contribution Graph

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      - name: Generate Pacman
        uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}

      - name: Push generated files
        uses: EndBug/add-and-commit@v9
        with:
          message: "chore: update pacman contribution graph"
          add: "output"
