# ⏱️ Cronômetro

Um cronômetro simples feito com HTML, CSS e JavaScript puro, que roda direto no navegador, sem precisar instalar nada. Ele permite iniciar, pausar, continuar, zerar e marcar tempos parciais (voltas).

## 🚀 Funcionalidades

* **▶️ Iniciar / Pausar / Continuar:** Um único botão inteligente que alterna entre os estados, mudando de ícone conforme a ação.
* **🔄 Resetar:** Zera o tempo acumulado, apaga o histórico de marcas e restaura o botão principal para o estado inicial.
* **🚩 Marcar tempo:** Registra o tempo exato do clique e o adiciona a uma lista numerada (*"Marca 1", "Marca 2", ...*).
* **🔢 Formato Preciso:** Exibição do tempo no formato `HH:MM:SS:CC` (horas, minutos, segundos e centésimos).

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Uso |
| :--- | :--- |
| **HTML5** | Estrutura da página (display, botões e lista de marcas) |
| **CSS3** | Estilização responsiva (layout com Flexbox, gradiente de fundo e cronômetro circular) |
| **JavaScript (ES6)** | Lógica de contagem e manipulação do DOM |
| **Font Awesome** | Ícones vetoriais para os botões (carregados via CDN) |

## 📂 Estrutura do Projeto

```text
Cronometro/
├── index.html   # Estrutura e marcação da página
├── style.css    # Design e identidade visual
├── script.js    # Lógica de funcionamento do cronômetro
└── README.md    # Documentação do projeto
```

## 💻 Como Executar

1. Baixe os arquivos ou clone este repositório.
2. Abra a pasta do projeto e dê um duplo clique no arquivo `index.html` (ou arraste-o para dentro do seu navegador de preferência).
3. **Pronto!** O projeto rodará instantaneamente sem necessidade de servidores locais ou instalação de dependências.

> ⚠️ **Nota:** É necessário estar conectado à internet para que os ícones dos botões sejam renderizados corretamente, já que o framework Font Awesome é importado via CDN.

## 🕹️ Como Usar

| Botão | Ação |
| :---: | :--- |
| 🔄 | Reinicia o cronômetro para o estado zero e limpa todo o histórico de marcas. |
| ▶️ / ⏸️ | Botão dinâmico que inicia, pausa ou retoma a contagem do tempo. |
| 🚩 | Captura o tempo atual e o salva na lista de marcas na tela. |

## 🧠 Como Funciona (Resumo do Código)

* **Controle do Tempo:** O tempo decorrido é armazenado em uma variável numérica chamada `timer`, incrementada em centésimos de segundo.
* **Precisão:** Um método `setInterval` configurado para disparar a cada 10 milissegundos adiciona `+1` ao contador principal e atualiza a interface de usuário.
* **Formatação:** A função `formatTime` divide o valor total de centésimos em blocos de horas, minutos, segundos e centésimos correspondentes, aplicando a propriedade `padStart` para garantir o preenchimento com zeros à esquerda quando necessário.
* **Máquina de Estados:** O botão principal gerencia suas ações por meio do atributo personalizado `action` (`start`, `pause` ou `continue`), que define o comportamento da função `toggleTimer` a cada clique.
* **Histórico:** As voltas capturadas são empurradas para dentro de um array `marks` e renderizadas dinamicamente dentro da tag `div#marks-list`.
