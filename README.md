# 🃏 Cartas de Confronto

Cartas de Confronto é um Hero Brawler Card Game tático baseado em turnos, projetado para rodar diretamente no navegador, sem necessidade de instalação. O jogo pode ser jogado em modo *Singleplayer* contra bots de IA (com múltiplas dificuldades) ou em modo *Multiplayer Online* conectando dois computadores via PeerJS.

## 📖 Como a Ideia Nasceu (O Processo)

O projeto nasceu da minha vontade de transformar um simples baralho de 54 cartas comum em um jogo de turnos dinâmico, onde cada naipe representasse uma classe heroica única (Cavaleiro, Besta, Paladino e Mago), cada número fosse um ataque ou defesa, e as cartas da corte (Valete, Dama, Rei e Ás) alterassem as regras do campo de batalha (Terrenos).

A ideia original era criar algo que pudesse ser jogado na mesa da escola/faculdade ou no computador. Acabei decidindo criar a versão digital em HTML, CSS e JavaScript utilizando o editor VS Code.

## 🛠️ Tecnologias Utilizadas

*   **HTML5 / CSS3 (Tailwind CSS):** Estrutura e estilização da interface gráfica responsiva (Mobile e Desktop).
*   **JavaScript (Vanilla):** Lógica do jogo, sistema de turnos, baralho, cooldown de habilidades e inteligência artificial dos bots.
*   **Web Audio API:** Para gerar sons de ambiente de masmorra e efeitos sonoros suaves nativamente (sem arquivos MP3 externos).
*   **PeerJS (WebRTC):** Tecnologia que permite criar salas e conectar dois jogadores via internet diretamente pelos seus navegadores.
*   **ChatGPT (DALL-E):** Responsável por gerar as incríveis artes de avatar das 4 classes do jogo.
*   **Google Gemini (IA):** Atuou como meu parceiro de programação (Co-piloto), ajudando a converter as minhas regras lógicas em código, estruturar a arquitetura e implementar sistemas de segurança.

## ⛰️ Os Desafios e as Soluções (Evolução do Jogo)

Durante o desenvolvimento e os testes de gameplay, enfrentei vários desafios de design e programação que exigiram atualizações (Patches):

1.  **Bug das Imagens Quebradas:** No início, tentei puxar imagens direto da web, o que resultou em "buldogues" aleatórios aparecendo como Cavaleiros. **Solução:** O Gemini me orientou a gerar as imagens, salvar localmente na mesma pasta do `index.html` e referenciá-las diretamente.
2.  **Balanceamento Assimétrico:** A vida inicial de 30/40 para todos estava deixando o jogo injusto. A "Besta" morria rápido pelo próprio dano de recuo, e o "Paladino" ficava imortal curando todo turno. **Solução:** Criamos vidas baseadas em classe: Besta (50 HP), Cavaleiro (40 HP), Paladino e Mago (30 HP), e nerfamos a quantidade base de cura e escudo.
3.  **Monotonia de Habilidades (O Poder Supremo):** Usar a habilidade especial todo turno por 2 AP travava o ritmo do jogo. **Solução:** Implementação de um sistema de "Cooldown". Agora o Poder Supremo fica bloqueado e só carrega a cada 5 turnos. Quando pronto, ele não custa AP (Grátis) e causa um efeito massivo (ex: +4 Cura, 6 Dano Perfurante, etc.).
4.  **Ritmo de Jogo Lento:** Jogadores demoravam muito a pensar no multiplayer. **Solução:** Adicionado um Timer rigoroso de 15 segundos; se o tempo esgotar, o turno é passado automaticamente.
5.  **Acidentes no Navegador:** Clicar em botões sem querer arruinava partidas. **Solução:** Implementação de modais de confirmação críticos para "Recomeçar" e "Sair".
6.  **Proteção de Código:** Como o jogo roda via GitHub Pages (Front-end), o código ficava exposto. **Solução:** Criação de um script de segurança simples que bloqueia o clique com o botão direito do mouse e atalhos de inspeção/cópia (Ctrl+U, Ctrl+C, Ctrl+S) para dificultar o roubo do projeto.

## 🤝 Créditos

*   **Idealização, Game Design e Balanceamento:** Pedro Henrique Alves
*   **Programação / Co-desenvolvimento:** Google Gemini
*   **Arte / Ilustração:** OpenAI (ChatGPT / DALL-E)
*   **Desenvolvido utilizando:** VS Code e hospedado no GitHub Pages.
