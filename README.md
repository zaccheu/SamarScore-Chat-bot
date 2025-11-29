# SamarScore-Chat-bot

Projeto de chat bot realizado pelo grupo SamarScore da turma de EC 6 da Faculdade Engenheiro Salvador Arena.

# Integrantes:

Arthur Destro — 81230047 — 081230047@faculdade.cefsa.edu.br  
Gustavo Alves — 81230023 — 081230023@faculdade.cefsa.edu.br  
Gustavo Mauriz — 81230040 — 081230040@faculdade.cefsa.edu.br  
Samar Victor — 81230035 — 081230035@faculdade.cefsa.edu.br  
Vinicius Strazza — 81230036 — 081230036@faculdade.cefsa.edu.br  
Vitor Barbosa — 81230037 — 081230037@faculdade.cefsa.edu.br

# Link do vídeo:

 https://www.youtube.com/watch?v=uLmTkLxW6Kg 

# Descrição Técnica do Projeto

Este circuito demonstra a aplicação prática de componentes digitais fundamentais, como memórias ROM, contadores, comparadores e flip-flops, para a construção de uma máquina de estados finitos capaz de processamento de texto e interação humano-máquina simplificada.

Arquitetura do Sistema

O circuito principal (main) centraliza o fluxo de dados através de um barramento comum de 7 bits, o qual conecta o periférico de entrada (Keyboard) aos módulos de processamento. A exibição dos dados ocorre em um periférico de saída de texto (TTY). A estrutura interna é segmentada em dois tipos de subcircuitos: Detectores e Respostas.

Módulos Detectores

O sistema possui trinta módulos de detecção (Detector_1 a Detector_30). Cada detector monitora continuamente o barramento de entrada. O funcionamento interno destes módulos utiliza contadores e memórias somente de leitura (ROM) para comparar, caractere a caractere, a entrada do usuário com uma sequência pré-gravada. Ao identificar uma correspondência exata com a frase armazenada, o detector aciona um sinal de nível lógico alto (flag de "Frase Detectada").

Módulos de Resposta

Associados a cada detector, existem trinta módulos de resposta (Resposta_1 a Resposta_30). Quando um detector valida uma entrada, o sinal de controle ativa o módulo de resposta correspondente. Estes subcircuitos utilizam contadores para percorrer uma ROM interna contendo a frase de resposta, transmitindo os caracteres sequencialmente para o terminal de saída (TTY).

Fluxo de Execução

O funcionamento do circuito segue o ciclo descrito abaixo:

    O usuário insere caracteres através do componente Keyboard.

    Os dados trafegam pelo barramento e são analisados simultaneamente por todos os detectores.

    Caso a sequência de entrada corresponda a uma das frases programadas, o detector específico envia um sinal de ativação (trigger).

    O módulo de resposta associado assume o controle e envia a mensagem de retorno ao display TTY.

    O sistema reinicia o ciclo de detecção para novas entradas.