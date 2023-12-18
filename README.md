<h1 align="center"> Tic-Tac-Toe Xo Transactions </h1>

<div align="center">
 <a href="#about">Sobre</a> |
 <a href="#installation">Como executar</a> |
 <a href="#author">Autor</a>
</div>

<h2 id="about">💡&nbsp; Sobre o projeto</h2>

<p>
  Esta implementação do jogo da velha (Noughts and Crosses) em uma blockchain Sawtooth é um exemplo prático que demonstra a funcionalidade desta plataforma.
</p>

<p>
  XO é um exemplo de família de transações que implementa o jogo da velha, também conhecido como Noughts and Crosses ou X's e O's. Esta família de transações destaca as capacidades e a flexibilidade do Sawtooth, proporcionando uma base para a construção de outros processadores de transações.
</p>

<p>
  Sawtooth é uma plataforma de blockchain de código aberto desenvolvida pela Linux Foundation. Projetada para fornecer uma estrutura robusta e flexível, Sawtooth facilita a criação, implementação e execução de redes de blockchain distribuídas. Seu design modular, flexibilidade e escalabilidade fazem dela uma escolha poderosa para o desenvolvimento de aplicações específicas, permitindo a personalização das regras de consenso.
</p>

---

<h2 id="installation">🚀&nbsp; Como executar </h2>

<b> É NECESSÁRIO TER O <a href="https://docs.docker.com/engine/install/">DOCKER</a> E O <a href="https://docs.docker.com/compose/install/compose-plugin/">DOCKER COMPOSE</a> INSTALADO PARA EXECUTAR. <b>

```bash
# Clone o repositório
git clone git@github.com:the-riquelme/tic-tac-toe-xo-transactions.git

# Suba os containers
docker compose -f docker/sawtooth-default.yaml up

# Entrar no bash do container principal de execucao:
docker exec -it sawtooth-shell-default bash

# Crie chaves para dois jogadores jogarem:
sawtooth keygen jack
sawtooth keygen jill

# Crie um jogo chamado my-game para dois jogadores passando p jogador 1:
xo create my-game --username jack --url http://rest-api:8008

# Este diagrama mostra o número de cada espaço no jogo da velha.
 1 | 2 | 3
---|---|---
 4 | 5 | 6
---|---|---
 7 | 8 | 9

# Jogue com o Jogador 1
xo take my-game 5 --username jack --url http://rest-api:8008

# Jogue com o Jogador 2
xo take my-game 1 --username jill --url http://rest-api:8008

# Mostrar o tabuleiro de jogo atual
xo show my-game --url http://rest-api:8008
GAME:     : my-game
PLAYER 1  : 02403a
PLAYER 2  : 03729b
STATE     : P1-NEXT

  O |   |
 ---|---|---
    | X |
 ---|---|---
    |   |

# Vencedor
GAME:     : my-game
PLAYER 1  : 0279e5
PLAYER 2  : 03b245
STATE     : P1-WIN

  O | O |  
 ---|---|---
  X | X | X
 ---|---|---
    |   |  

# Exclua o jogo
xo delete my-game --url http://rest-api:8008
```

---

<h2 id="author">👨‍💻&nbsp; Autor</h2>

<b>👤 Riquelme Damião Silva<b>

<div style="display: inline_block">
  <a href="https://www.linkedin.com/in/riquelme-damiao-silva/" target="_blank">
   <img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank">
  </a>
  <a href="mailto:riquelmedamiaosilva@gmail.com" target="_blank">
    <img src="https://img.shields.io/badge/gmail-D14836?&style=for-the-badge&logo=gmail&logoColor=white"/>
  </a>
</div>
