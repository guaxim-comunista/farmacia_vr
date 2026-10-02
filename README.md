Crie um jogo web completo chamado "Fiscal da Farmácia VR".

Quero um jogo educativo de inspeção de segurança em uma farmácia/laboratório,
feito para funcionar em celulares colocados em óculos VR tipo Google Cardboard.

TECNOLOGIAS:
- HTML5
- CSS3
- JavaScript ES6+
- Web APIs
- DeviceOrientation API
- LocalStorage
- GitHub Pages
- Não utilizar backend.
- Não utilizar frameworks obrigatoriamente.
- O projeto deve funcionar abrindo index.html e também no GitHub Pages.

OBJETIVO:
O jogador deve entrar em um laboratório/farmácia virtual e encontrar problemas
de segurança, organização e utilização de EPI.

IMPORTANTE:
A imagem da cena NÃO pode possuir círculos, setas, números ou qualquer
indicação visual dos erros.

O jogador precisa descobrir os erros sozinho.

=========================
MODO VR
=========================

Criar modo estereoscópico para Cardboard.

Dividir a tela em duas áreas:

LEFT EYE
RIGHT EYE

Cada olho deve mostrar a cena com pequena diferença de posição para produzir
efeito estereoscópico.

Usar DeviceOrientation API para movimentação da câmera.

Implementar:
- gamma para movimento horizontal;
- beta para movimento vertical;
- controle de sensibilidade;
- suavização do movimento;
- limite vertical;
- requestPermission quando o navegador exigir;
- fallback caso o sensor não esteja disponível.

Adicionar uma cruz no centro da tela.

A cruz representa a mira do jogador.

Quando a mira estiver sobre um objeto investigável, mostrar discretamente:

"INVESTIGAR"

Sem indicar se o objeto é correto ou incorreto.

=========================
SISTEMA DE JOGO
=========================

Criar 4 níveis:

NÍVEL 1:
7 erros
60 segundos

NÍVEL 2:
10 erros
90 segundos

NÍVEL 3:
15 erros
120 segundos

NÍVEL 4:
20 erros
180 segundos
Eventos aleatórios habilitados.

A dificuldade deve aumentar progressivamente.

=========================
INVESTIGAÇÃO
=========================

Cada erro deve ser um objeto investigável.

Quando o jogador clicar/tocar em uma área:

Abrir uma interface:

"INVESTIGAR SITUAÇÃO"

Mostrar pergunta e alternativas.

Exemplo:

"O que está inadequado nesta situação?"

A
B
C
D

O jogador deve escolher uma alternativa.

Não revelar a resposta antes da escolha.

Se acertar:
+100 pontos.

Se for um erro difícil:
+200 pontos.

Se errar:
-50 pontos
-10 segundos.

Depois de 3 erros:
penalidade adicional de -100 pontos.

Se cometer erro grave:
perder uma vida.

=========================
VIDAS
=========================

Começar com:

❤️ ❤️ ❤️

Erros graves podem retirar uma vida.

Quando chegar a zero:

GAME OVER.

Mostrar tela:

"MISSÃO FALHOU"

Mostrar estatísticas.

=========================
PONTUAÇÃO
=========================

Sistema:

Erro normal:
+100

Erro difícil:
+200

Evento correto:
+150

Resposta rápida:
+50

Combo:
+25 por nível de combo

Erro:
-50

Erro grave:
-150

Erro de investigação:
-10 segundos

A cada 3 erros:
-100 pontos extras

Criar combo.

Exemplo:

1 acerto = x1
2 acertos consecutivos = x2
3 = x3
4 = x4
5 = x5

Se errar, resetar combo.

=========================
EVENTOS ALEATÓRIOS
=========================

No nível 4 criar eventos.

Eventos possíveis:

1. Derramamento na bancada.

2. Equipamento superaquecendo.

3. Resíduo descartado incorretamente.

4. Porta de emergência aberta.

5. Falta de EPI.

6. Objeto bloqueando passagem.

7. Material fora do armário.

8. Alerta de higiene.

Cada evento deve apresentar uma situação e exigir uma decisão rápida.

Criar contagem regressiva para eventos.

Se o jogador resolver corretamente:
+150 pontos.

Se ignorar:
perder pontos.

=========================
ERROS
=========================

Criar pelo menos 20 erros.

Exemplos:

- armário aberto;
- medicamento fora do local;
- objeto fora da bancada;
- profissional sem luvas;
- profissional sem máscara;
- EPI inadequado;
- resíduo no local errado;
- porta aberta;
- equipamento ligado incorretamente;
- objeto bloqueando passagem;
- recipiente sem identificação;
- material fora do armário;
- bancada desorganizada;
- produto próximo da pia;
- lixo inadequado;
- material de limpeza no lugar errado;
- sinalização ignorada;
- equipamento sem proteção;
- objeto pessoal na bancada;
- procedimento incorreto.

Cada erro deve possuir:

id
nome
posição
tamanho da área
dificuldade
pergunta
alternativas
resposta correta
pontuação
penalidade
tipo

Armazenar isso em data/errors.json.

=========================
MAPA
=========================

Criar uma estrutura de laboratório com:

- bancada;
- armários;
- estoque;
- pia;
- equipamentos;
- lixeira;
- área de EPI;
- porta;
- área de circulação.

Criar pelo menos 4 setores.

O jogador deve conseguir olhar para diferentes regiões.

=========================
HUD
=========================

No topo:

FISCAL DA FARMÁCIA VR

Mostrar:

⏱ TEMPO
🔎 ERROS
❤️ VIDAS
⭐ PONTOS
🔥 COMBO

No canto inferior:

instruções discretas.

Não ocupar a tela inteira.

=========================
TELAS
=========================

Criar:

1. Menu inicial.

2. Tutorial.

3. Seleção de dificuldade.

4. Modo VR.

5. Tela de investigação.

6. Evento aleatório.

7. Pausa.

8. Vitória.

9. Game Over.

10. Resultado final.

=========================
RESULTADO FINAL
=========================

Mostrar:

MISSÃO CONCLUÍDA

Pontos:
XXXX

Erros encontrados:
XX/XX

Erros cometidos:
XX

Tempo restante:
XX

Combo máximo:
XX

Precisão:
XX%

Criar classificação:

S
A
B
C
D

Essa classificação deve ser calculada matematicamente com base na
pontuação e precisão.

=========================
SALVAMENTO
=========================

Usar LocalStorage.

Salvar:

melhor pontuação
maior combo
melhor precisão
níveis desbloqueados
última dificuldade
configurações de áudio

Criar botão:

"ZERAR PROGRESSO"

=========================
ÁUDIO
=========================

Criar sistema centralizado de áudio.

Arquivos:

click.mp3
success.mp3
error.mp3
warning.mp3
victory.mp3
gameover.mp3

Se os arquivos não existirem, o jogo deve continuar funcionando sem áudio.

=========================
DESIGN
=========================

Quero aparência de jogo moderno de treinamento VR.

Tema:

farmácia/laboratório futurista.

Usar:

azul escuro
ciano
branco
cinza
vermelho para alertas
verde para acertos

HUD com aparência tecnológica.

Animações suaves.

Efeitos:

glow
fade
scale
shake
pulse

Não exagerar nas animações.

=========================
RESPONSIVIDADE
=========================

Funcionamento:

desktop
celular
tablet

No celular:

modo VR.

No desktop:

modo demonstração.

Detectar orientação da tela.

Se estiver em portrait:

mostrar aviso:

"Vire o celular para horizontal."

=========================
ARQUITETURA
=========================

Não colocar todo o código em um único arquivo.

Usar:

js/main.js
js/game.js
js/vr.js
js/player.js
js/investigation.js
js/events.js
js/scoring.js
js/timer.js
js/audio.js
js/storage.js

Criar classes quando fizer sentido.

Exemplo:

GameManager
VRManager
InvestigationManager
EventManager
ScoreManager
AudioManager
StorageManager

Manter responsabilidades separadas.

=========================
ACESSIBILIDADE
=========================

Adicionar:

controle de volume;
opção de reduzir animações;
alto contraste;
tamanho de texto;
modo sem áudio.

=========================
GITHUB PAGES
=========================

O projeto deve funcionar diretamente no GitHub Pages.

Não usar servidor.

Não utilizar caminhos absolutos.

Todos os caminhos devem ser relativos.

=========================
IMAGEM
=========================

Existe uma imagem chamada:

assets/images/farmacia_vr.png

Utilizar essa imagem como referência/cenário inicial.

A imagem não possui marcações dos erros.

Não desenhar círculos vermelhos.

Não desenhar setas.

Não mostrar antecipadamente os erros.

=========================
ENTREGA
=========================

Crie todos os arquivos.

Crie README.md com:

- descrição;
- objetivo;
- tecnologias;
- como executar;
- como publicar no GitHub Pages;
- como utilizar no celular;
- como utilizar com Cardboard;
- arquitetura;
- regras do jogo.

Depois teste o projeto procurando erros de JavaScript,
links quebrados, caminhos incorretos e problemas de responsividade.

Se encontrar erros, corrija-os antes de finalizar.

O resultado deve parecer um projeto acadêmico profissional,
mas continuar fácil de entender e modificar.
