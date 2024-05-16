# Hey 👋 What's up?

My name is Soumyadip Adak and I'm a Web Developer 

## 🔗 About me

✨ Creating bugs since Java <br>
📚 I'm currently learning Web Development and Python programming <br>
🎯 Goals: Full Stack Web Developer <br>
😄 Fun fact: I love writing code in Java <br>

### Social Media links 👇

<p align="left">
    <a href="https://www.linkedin.com/in/soumyadip-adak-a19b03281/"><img src="linkedin.png" alt="LinkedIn Icon" width="30px" height="auto"></a>
    <a href="https://www.instagram.com/soumyadip_adak8888"><img src="instagram.png" alt="Instagram Icon" width="30px" height="auto"></a>
    <a href="https://www.facebook.com/soumyadip.adak.99"><img src="facebook.png" alt="Facebook Icon" width="30px" height="auto"></a>
</p>

## I code with

<p align="left">
    <img src="java.png" alt="Java Icon" width="50px" height="50px">
    <img src="javascript.png" alt="JavaScript Icon" width="50px" height="auto">
    <img src="html.png" alt="HTML5 Icon" width="50px" height="auto">
    <img src="css.png" alt="CSS3 Icon" width="50px" height="auto">
</p>

<yml>name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}</yml>
