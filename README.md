# Hi, I'm Klymora! <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="30px">

⛏️ Crypto mining & automation  
🤖 AI-powered bots & scripts  
💾 Blockchain & open-source  

name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"  # Menjalankan setiap hari pada tengah malam UTC

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v2

      - name: Generate Snake Animation
        uses: Platane/snk@master
        with:
          github_user_name: Klymora
          svg_out_path: dist/github-contribution-grid-snake.svg

      - name: Publish to GitHub Pages
        uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
