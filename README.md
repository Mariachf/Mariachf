## Olá, me chamo Maria Eduarda!!
### Seja bem vindos ao meu perfil GitHub 👋

- 🖥 Atualmente trabalho com PC gamer Montagem e venda
- 🌱 Estou entrendo no mundo DEV agora então sou bem Iniciante
- 🤔 Estou procurando ajuda com tudo no momento, então quem poder dar dicas ou apoio vou ficar muito feliz
- 📫 Como entrar em contato comigo: whats - (11) 96194-2832 ou email - me72068@gmail.com 
- 🙂 curiosidade sobre mim: sou formada em getão de recursos Humanos 

<div align="center">
  <a href="https://github.com/Mariachf">
  <img height="160cm" src="https://github-readme-stats.vercel.app/api?username=Mariachf&show_icons=true&theme=gotham&include_all_commits=true&count_private=true"/>
  <img height="160cm" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Mariachf&layout=compact&langs_count=7&theme=gotham"/>
</div>
  
 
# Nome da Actions:  
name: Snake Game

# Controlador do tempo que sera feito a atualização dos arquivos.
on:
  schedule:
      # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

# Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Repositorio que será utilizado para gerar os arquivos.
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: Mariachf #Seu usuario
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      # Para as atualizações.
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
