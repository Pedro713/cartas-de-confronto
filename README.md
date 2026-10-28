# 🃏 Cartas de Confronto

**Cartas de Confronto** é um *Hero Brawler Card Game* tático baseado em turnos, projetado para rodar diretamente no navegador, sem necessidade de instalação. O jogo pode ser jogado em modo **Singleplayer** contra bots de IA (com múltiplas dificuldades) ou em modo **Multiplayer Online** conectando dois computadores via PeerJS.

## 📖 Como a Ideia Nasceu (O Processo)

O projeto nasceu da minha vontade de transformar um simples baralho de 54 cartas comum em um jogo de turnos dinâmico, onde cada naipe representasse uma classe heroica única (**Cavaleiro**, **Besta**, **Paladino** e **Mago**), cada número fosse um ataque ou defesa, e as cartas da corte (Valete, Dama, Rei e Ás) alterassem as regras do campo de batalha (**Terrenos**).

A ideia original era criar algo que pudesse ser jogado na mesa da escola/faculdade ou no computador. Acabei decidindo criar a versão digital em HTML, CSS e JavaScript utilizando o editor VS Code.

## 🛠️ Tecnologias e Dependências Utilizadas

* **HTML5 / CSS3 (Tailwind CSS):** Estrutura e estilização da interface gráfica responsiva (Mobile e Desktop).
* **JavaScript (Vanilla):** Lógica do jogo, sistema de turnos, baralho, cooldown de habilidades e inteligência artificial dos bots.
* **Web Audio API:** Para gerar sons de ambiente de masmorra e efeitos sonoros suaves nativamente (sem arquivos MP3 externos).
* **PeerJS (WebRTC):** Biblioteca que permite criar salas e conectar dois jogadores via internet diretamente pelos seus navegadores.
* **Canvas Confetti:** Biblioteca leve para animação de partículas e confetes na tela de vitória.
* **ChatGPT (DALL-E):** Responsável por gerar as artes de avatar das 4 classes do jogo.
* **Google Gemini (IA):** Atuou como parceiro de programação (Co-piloto), auxiliando a converter as regras lógicas em código e estruturar a arquitetura.

## ⛰️ Os Desafios e as Soluções (Evolução do Jogo)

Durante o desenvolvimento e os testes de gameplay, enfrentei vários desafios de design e programação que exigiram atualizações (Patches):

* **Bug das Imagens Quebradas:** No início, tentei puxar imagens direto da web, o que resultou em imagens aleatórias aparecendo como Cavaleiros. **Solução:** Gerar as imagens das classes, salvar localmente na mesma pasta do `index.html` e referenciá-las diretamente.
* **Balanceamento Assimétrico:** A vida inicial igual para todos deixava o jogo injusto. A "Besta" morria rápido pelo próprio dano de recuo, e o "Paladino" ficava imortal curando todo turno. **Solução:** Criamos vidas baseadas em classe: Besta (50 HP), Cavaleiro (40 HP), Paladino e Mago (30 HP), além de ajustar a quantidade base de cura e escudo.
* **Monotonia de Habilidades (O Poder Supremo):** Usar a habilidade especial todo turno por 2 AP travava o ritmo do jogo. **Solução:** Implementação de um sistema de *Cooldown*. Agora o Poder Supremo fica bloqueado e só carrega a cada 5 turnos. Quando pronto, ele não custa AP (Grátis) e causa um efeito massivo (ex: +4 Cura, 6 Dano Perfurante, etc.).
* **Ritmo de Jogo Lento:** Jogadores demoravam muito a pensar no multiplayer. **Solução:** Adicionado um Timer rigoroso de 15 segundos; se o tempo esgotar, o turno é passado automaticamente.
* **Acidentes no Navegador:** Clicar em botões sem querer arruinava partidas. **Solução:** Implementação de modais de confirmação críticos para "Recomeçar" e "Abandonar".

## 📜 Licenciamento e Dependências de Terceiros

Este projeto é distribuído sob a **Licença MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

Abaixo está o mapeamento das três dependências externas utilizadas no código (`index.html`):

| Nome | Licença | Permite uso comercial? | Obriga abrir o derivado? |
| :--- | :--- | :--- | :--- |
| **Tailwind CSS** | MIT | Sim | Não |
| **PeerJS** (`peerjs@1.5.2`) | MIT | Sim | Não |
| **Canvas Confetti** (`canvas-confetti@1.9.3`) | ISC | Sim | Não |

## 🤝 Créditos

* **Idealização, Game Design e Desenvolvimento:** Pedro Henrique Alves
* **Co-desenvolvimento / Assistência de Código:** Google Gemini
* **Arte / Ilustração:** OpenAI (DALL-E)
* **Hospedagem:** GitHub Pages
