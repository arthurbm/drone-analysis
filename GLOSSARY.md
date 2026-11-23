# Análise de vibração de drones (DronePropB)

Vocabulário do projeto de Sinais e Sistemas que compara sinais de vibração de drones com hélices saudáveis e danificadas, nos domínios do tempo e da frequência. Vale para o notebook, o relatório e as conversas do grupo.

## Language

### Dados

**Registro**:
Um ensaio gravado, guardado em um arquivo `.mat` do dataset; contém o sinal do piezo e, na maioria dos casos, os da IMU e a tensão da bateria.
_Avoid_: arquivo (quando se fala do ensaio), experimento, gravação, amostra

**Janela**:
Trecho de 1 s de um registro, sem sobreposição com os vizinhos; é a unidade em que as características são calculadas.
_Avoid_: trecho, segmento, amostra, frame

**Amostra**:
Um único valor medido pelo sensor em um instante.
_Avoid_: ponto, leitura; não usar para janela nem para registro

**Piezo**:
Acelerômetro piezoelétrico de um único eixo, de direção não documentada; é o sensor da análise principal.
_Avoid_: acelerômetro (sozinho), 4º eixo, AccData

**IMU**:
Unidade inercial do drone, que mede a aceleração em três eixos (x, y, z); usada só na investigação adicional.
_Avoid_: acelerômetros onboard

**Eixo**:
Direção de medição de um sensor. A IMU tem três; o piezo tem um, e por isso não é contado como "um dos eixos".

**Tensão da bateria**:
Tensão elétrica da bateria do drone registrada durante o ensaio; é uma condição de operação, não uma medida de vibração.
_Avoid_: bateria (sozinho), voltagem

### Condições

**Condição**:
Estado da hélice em um registro, com dois valores possíveis: saudável ou danificada.
_Avoid_: classe (fora do contexto de classificação), estado, rótulo

**Saudável**:
Hélice sem defeito (código `F0`).
_Avoid_: normal, boa, sem falha

**Danificada**:
Hélice com qualquer um dos defeitos do dataset (códigos `F1`, `F2` e `F3`).
_Avoid_: defeituosa, com defeito, com falha

**Grupo de falha**:
Tipo de defeito da hélice danificada: `F1`, `F2` ou `F3`. Grupos diferentes alteram o sinal de formas diferentes.
_Avoid_: tipo de falha, classe de falha, falha (sozinho)

**Severidade**:
Grau do defeito dentro de um grupo de falha: `SV1`, `SV2` ou `SV3`.
_Avoid_: nível, intensidade do dano

**Repetição**:
Um dos três registros saudáveis feitos nas mesmas condições (`R1`, `R2`, `R3`).

**Velocidade**:
Nível de velocidade de operação do ensaio (`SP1` a `SP3`); a rotação correspondente não é documentada.
_Avoid_: RPM, rotação

**Código C**:
Parte do nome do arquivo (`C1` a `C4`) cujo significado não é documentado pelos autores; registros com C diferentes não são misturados nas comparações.
_Avoid_: canal, configuração, canal do acelerômetro

### Medidas

**Característica**:
Um número calculado a partir de uma janela para descrevê-la.
_Avoid_: feature, atributo, métrica, medida (quando há ambiguidade)

**Domínio**:
A forma de olhar o sinal: no tempo (valor a cada instante) ou na frequência (quanto de vibração há em cada frequência).

**Característica temporal**:
Característica calculada diretamente sobre os valores da janela ao longo do tempo.

**Característica espectral**:
Característica calculada sobre o espectro da janela.
_Avoid_: característica de frequência, característica frequencial

**Intensidade**:
O quanto o sinal vibra, independentemente de em quais frequências; é o que RMS, desvio padrão, potência e picos medem.
_Avoid_: amplitude (quando se fala do nível geral), força

**RMS**:
Raiz da média dos quadrados dos valores da janela; resume a intensidade da vibração em um número, na unidade do sinal.
_Avoid_: valor eficaz, média (são coisas diferentes)

**Potência média**:
Média dos quadrados dos valores da janela; é o RMS ao quadrado. Não é potência mecânica em watts.

**Fator de crista**:
Pico absoluto dividido pelo RMS; indica o quanto o maior valor se destaca do nível geral da janela.

**Espectro**:
Representação da janela que mostra a amplitude da vibração em cada frequência.
_Avoid_: FFT (é o algoritmo que calcula o espectro, não o resultado)

**Pico**:
Frequência em que o espectro tem um máximo local, isto é, uma componente periódica que se destaca.
_Avoid_: harmônico, linha (sem evidência do que a origina)

**Frequência dominante**:
Frequência do maior pico do espectro da janela.

**Banda**:
Faixa fixa de frequências, igual para todas as condições (B1 a B4).
_Avoid_: faixa, intervalo

**Potência na banda**:
Parcela da potência da janela que está dentro de uma banda, em valor absoluto.

**Fração na banda**:
Potência na banda dividida pela potência total da janela; descreve a forma do espectro sem depender da intensidade.
_Avoid_: potência relativa, percentual da banda

**Centroide espectral**:
Frequência média do espectro, ponderada pela potência em cada frequência; funciona como o "centro de massa" do espectro.

**Entropia espectral**:
Medida, entre 0 e 1, de quão espalhada a potência está entre as frequências: baixa quando concentrada em poucos picos, alta quando distribuída.

### Comparação

**Separação**:
O quanto os valores de uma característica diferem entre saudável e danificada.
_Avoid_: discriminação, poder preditivo

**d de Cohen**:
Diferença entre as médias de dois grupos, medida em desvios padrão; mede o tamanho da separação.

**AUC**:
Probabilidade de uma janela danificada, sorteada ao acaso, ter valor maior que uma saudável; 0,5 significa nenhuma separação.

**Redundância**:
Situação em que duas características trazem praticamente a mesma informação, medida pela correlação entre elas.

**Variável de confusão**:
Condição de operação que difere entre saudáveis e danificadas e pode explicar uma diferença observada no lugar do defeito; neste recorte, a tensão da bateria.
_Avoid_: viés, ruído
