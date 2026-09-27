# 🃏 Cartas de Confronto

**Cartas de Confronto** é um Hero Brawler Card Game tático baseado em turnos, projetado para rodar diretamente no navegador, sem necessidade de instalação. O jogo pode ser jogado em modo *Singleplayer* contra bots de IA (com múltiplas dificuldades) ou em modo *Multiplayer Online* conectando dois computadores via PeerJS.

## 📖 Como a Ideia Nasceu (O Processo)
O projeto nasceu da minha vontade de transformar um simples baralho de 54 cartas comum em um jogo de turnos dinâmico, onde cada naipe representasse uma classe heroica única (Cavaleiro, Besta, Paladino e Mago), cada número fosse um ataque ou defesa, e as cartas da corte (Valete, Dama, Rei e Ás) alterassem as regras do campo de batalha (Terrenos).

A ideia original era criar algo que pudesse ser jogado na mesa da escola/faculdade ou no computador. Acabei decidindo criar a versão digital em HTML, CSS e JavaScript utilizando o editor **VS Code**.

### 🛠️ Tecnologias Utilizadas
* **HTML5 / CSS3 (Tailwind CSS):** Estrutura e estilização da interface gráfica responsiva.
* **JavaScript (Vanilla):** Lógica do jogo, sistema de turnos, baralho e inteligência artificial dos bots.
* **Web Audio API:** Para gerar sons de ambiente de masmorra e efeitos sonoros suaves (sem necessidade de arquivos MP3 externos).
* **PeerJS (WebRTC):** Tecnologia que permite criar salas e conectar dois jogadores via internet diretamente pelos seus navegadores.
* **ChatGPT (DALL-E):** Responsável por gerar as incríveis artes de avatar das 4 classes do jogo.
* **Google Gemini (IA):** Atuou como meu parceiro de programação (Co-piloto), ajudando a converter as minhas regras lógicas em código JavaScript, estruturar a arquitetura do jogo e refinar os sistemas.

## ⛰️ Os Desafios e as Soluções

Durante o desenvolvimento, enfrentei vários desafios de design e programação:

1. **Bug das Imagens Quebradas:** No início, tentei puxar imagens direto da web, o que resultou em "buldogues" aleatórios aparecendo como Cavaleiros. **Solução:** O Gemini me orientou a gerar as imagens no ChatGPT, salvar localmente na mesma pasta do `index.html` e referenciá-las diretamente, resolvendo o bug visual.
2. **Balanceamento de Dano vs Vida:** A classe "Besta" estava finalizando os jogos em 3 ou 4 turnos com ataques absurdos. A vida inicial de 30 era pouca. **Solução:** Elevamos a vida máxima para 40 HP, nerfamos o dano explosivo da Besta e demos a ela um dano de recuo (pagando o preço do alto dano com a própria vida), o que fez as partidas chegarem a durar 10+ rodadas muito mais disputadas.
3. **Imersão Sonora Estridente:** A primeira versão de áudio do jogo usava osciladores puros que geravam sons muito robóticos e estridentes ("bips"). **Solução:** Substituímos por frequências controladas, simulando som macio de feltro ao bater cartas e um ambiente de "vento de masmorra" mais orgânico para a trilha sonora.
4. **Acidentes no Navegador:** Clicar em botões sem querer arruinava partidas avançadas. **Solução:** Implementação de modais de confirmação críticos para "Recomeçar" e "Sair", inclusive exigindo votação entre jogadores no modo Multiplayer.

## 🤝 Créditos
* **Idealização e Game Design:** Pedro Henrique Alves
* **Programação / Co-desenvolvimento:** Google Gemini
* **Arte / Ilustração:** OpenAI (ChatGPT / DALL-E)
* **Desenvolvido utilizando:** VS Code e hospedado no GitHub Pages.
