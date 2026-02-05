<!-- =========================
   Pushkal Pratap Singh — GitHub Profile README
   Repo name MUST be: xpushkal
   File: README.md
========================= -->

<div align="center">

<h1>Pushkal Pratap Singh</h1>
<p><b>AI/ML Developer • Backend/Systems • RAG + Agentic Pipelines</b></p>

<a href="https://pushkal.me"><b>Portfolio</b></a> •
<a href="https://github.com/xpushkal"><b>GitHub</b></a> •
<a href="https://linkedin.com/in/pushkalx30/"><b>LinkedIn</b></a> •
<a href="mailto:pushkalx30@gmail.com"><b>Email</b></a>

<br/><br/>

<img src="https://komarev.com/ghpvc/?username=xpushkal&label=Profile%20views&color=0e75b6&style=flat" alt="profile views"/>

</div>

---

## 🛰️ Contribution Graph… but it’s a Space Shooter (auto-runs)

> Your GitHub contribution grid becomes enemies. A spaceship fights through it automatically.  
> **No snake. No pacman.**

<div align="center">

<!-- Once you set up the workflow (below), this file will exist in your repo -->
<img src="game.gif" alt="Space Shooter on my GitHub contributions" width="720"/>

</div>

<details>
<summary><b>⚙️ Setup (copy-paste workflow) — keep everything in one place</b></summary>

Create this file in your profile repo:

**`.github/workflows/update-game.yml`**
```yml
name: Update Space Shooter Game

on:
  schedule:
    - cron: "0 0 * * *"   # daily at 00:00 UTC
  workflow_dispatch:

permissions:
  contents: write

jobs:
  update-game:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Generate contribution game GIF
        uses: czl9707/gh-space-shooter@v1
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          output-path: "game.gif"
          strategy: "random"   # options: column | row | random
          fps: "40"

      - name: Commit updated GIF
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "41898282+github-actions[bot]@users.noreply.github.com"
          git add game.gif
          git commit -m "chore: update space shooter game" || exit 0
          git push
