<!-- Repo MUST be named: xpushkal
     File: README.md -->

<div align="center">

<h1>Pushkal Pratap Singh</h1>

<p>
  <b>Backend • AI/ML • Agentic AI • RAG • Microservices</b><br/>
  Lucknow, India • <a href="https://pushkal.me">pushkal.me</a>
</p>

<p>
  <a href="https://pushkal.me"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-pushkal.me-black"></a>
  <a href="https://github.com/xpushkal"><img alt="GitHub" src="https://img.shields.io/badge/GitHub-xpushkal-181717?logo=github"></a>
  <a href="https://linkedin.com/in/pushkalx30/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-pushkalx30-0A66C2?logo=linkedin&logoColor=white"></a>
  <a href="mailto:pushkalx30@gmail.com"><img alt="Email" src="https://img.shields.io/badge/Email-pushkalx30%40gmail.com-EA4335?logo=gmail&logoColor=white"></a>
</p>

<img src="https://komarev.com/ghpvc/?username=xpushkal&label=Profile%20views&style=flat" alt="profile views"/>

</div>

---

## 🚀 SpaceShip on my Contribution Grid (auto-updating)

<div align="center">
  <!-- This will start showing once you add the workflow below and it generates the file -->
  <img src="game.gif" alt="Space Shooter over contributions" width="800" />
</div>

<details>
<summary><b>✅ One-time setup: add the workflow that generates game.gif</b></summary>

Create this file in your profile repo:

**.github/workflows/space-game.yml**
```yml
name: Update Space Contribution Game

on:
  schedule:
    - cron: "0 0 * * *"     # daily
  workflow_dispatch:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repo
        uses: actions/checkout@v4

      - name: Generate space shooter GIF
        uses: czl9707/gh-space-shooter@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          output-path: "game.gif"
          strategy: "random"
          fps: "40"

      - name: Commit and push
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git add game.gif
          git commit -m "chore: update space game" || exit 0
          git push
