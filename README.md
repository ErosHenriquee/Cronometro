⏱️ Cronômetro

Um cronômetro simples feito com HTML, CSS e JavaScript puro, que roda direto no navegador, sem instalar nada. Ele permite iniciar, pausar, continuar, zerar e marcar tempos (voltas).

Funcionalidades
▶️ Iniciar / Pausar / Continuar: um único botão alterna entre os estados e o ícone muda conforme a ação.
🔄 Resetar: zera o tempo, apaga as marcas e volta o botão para o estado inicial.
🚩 Marcar tempo: registra o tempo atual e adiciona na lista ("Marca 1", "Marca 2", ...).
Exibição no formato horas:minutos:segundos:centésimos (HH:MM:SS:CC).
Tecnologias utilizadas
Tecnologia	Uso
HTML5	Estrutura da página
CSS3	Estilo (layout com Flexbox, gradiente de fundo, cronômetro circular)
JavaScript (ES6)	Lógica do cronômetro
Font Awesome	Ícones dos botões (carregado por CDN)
Estrutura do projeto
Cronometro/
├── index.html   # Estrutura da página (display, botões e lista de marcas)
├── style.css    # Estilização da página
├── script.js    # Lógica do cronômetro
└── README.md    # Documentação do projeto
Como executar
Baixe ou clone o projeto.
Abra o arquivo index.html no navegador (clique duas vezes ou arraste para o navegador).
Pronto! Não é necessário instalar dependências.

Obs.: é preciso ter conexão com a internet para os ícones aparecerem, pois o Font Awesome é carregado por CDN.

Como usar
Botão	Ação
🔄	Reinicia o cronômetro e limpa as marcas
▶️ / ⏸️	Inicia, pausa ou continua a contagem
🚩	Salva o tempo atual na lista de marcas
Como funciona (resumo do código)
O tempo é guardado em uma variável timer, contada em centésimos de segundo.
Um setInterval de 10 ms soma 1 ao timer e atualiza a tela.
A função formatTime converte o valor total em horas, minutos, segundos e centésimos, completando com zeros à esquerda (padStart).
O botão principal usa o atributo action (start, pause ou continue) para saber o que fazer ao ser clicado (função toggleTimer).
As marcas ficam em um array marks e são exibidas na div#marks-list.