# Repasse: ajustes nas outras seções

Correções pontuais nas seções 1, 2, 3 e 5 do notebook e no relatório, encontradas ao escrever e auditar a seção 4. São opcionais para quem escreveu cada seção: cada linha abaixo é uma troca independente, e nenhuma muda código de análise nem resultado.

Elas saem de três fontes:

- **o achado da tensão da bateria (seção 4.4):** quatro trechos atribuíam ao defeito o deslocamento dos picos ou a diferença entre condições (trocas 2, 12, 15 e 16 do Colab);
- **números do texto que não batiam com as tabelas** do próprio notebook, depois que ele foi executado do zero (seções 2.4, 3 e 5.4, e a tabela da IMU do relatório);
- **acabamento:** título de gráfico que dizia "filtrado" com o sinal bruto, dois títulos com erro de digitação e a opção `--id` do `gdown`, que as versões novas não aceitam.

## Colab

Em cada linha, procure o trecho atual na seção indicada e troque. A cópia `analise_vibracao_drones.ipynb` deste branch já está com todas aplicadas.

| # | Onde | Trecho atual | Trocar por |
|---|---|---|---|
| 1 | Primeira célula (download) | `!gdown --id 1l0AScHDbsGFCsKA72q3DCv4ZPBvyh-WW` | `!gdown 1l0AScHDbsGFCsKA72q3DCv4ZPBvyh-WW` |
| 2 | Seção 1.2, "Justificativa" | `Assim, as diferenças observadas podem ser atribuídas à condição da hélice, e não às condições de operação.` | `Assim, a comparação reduz a influência das condições de operação, mas não a elimina: a tensão da bateria difere entre os registros (seção 4.4).` |
| 3 | Seção 2.1, título do gráfico | `'Registro completo (piezo, SP3, C1, filtrado)'` | `'Registro completo (piezo, SP3, C1, sem filtro)'` |
| 4 | Seção 2.4 | `pico a pico 2,12 contra 1,89 m/s² (+12%)` | `pico a pico 2,11 contra 1,89 m/s² (+12%)` |
| 5 | Seção 2.4 | `O fator de crista quase não muda (3,77 contra 3,71).` | `O fator de crista quase não muda (3,76 contra 3,71).` |
| 6 | Seção 2.4 | `o F3 tem mediana até menor (≈ 0,19 m/s²)` | `o F3 tem mediana até menor (≈ 0,20 m/s²)` |
| 7 | Seção 2.4 | `RMS e picos também são fortemente correlacionados (r = 0,93 a 0,95).` | `RMS e picos também são fortemente correlacionados (r = 0,94 a 0,96).` |
| 8 | Seção 2.4 | `correlação moderada e negativa com o RMS (r = −0,52)` | `correlação moderada e negativa com o RMS (r = −0,53)` |
| 9 | Seção 2.4 | `e não se correlaciona com nenhuma outra medida (\|r\| ≤ 0,05).` | `e tem correlação fraca com as outras medidas (\|r\| ≤ 0,24).` |
| 10 | Seção 3.2, título | `### .**3.2 Plotando os Espectros**` | `### **3.2 Plotando os Espectros**` |
| 11 | Seção 3, "Interpretação do espectro" | `na condição saudável, 43,4% da potência está em B1` | `na condição saudável, 43,3% da potência está em B1` |
| 12 | Seção 3, "Interpretação do espectro" | `reduz a faixa de 200–335 Hz e desloca os picos principais para frequências um pouco menores.` | `reduz a faixa de 200–335 Hz; os picos principais também aparecem em frequências um pouco menores, mas isso acompanha a tensão da bateria (seção 4.4).` |
| 13 | Seção 3.6, título | `### **3.6 Eeito da Amostragem**` | `### **3.6 Efeito da Amostragem**` |
| 14 | Seção 5.4 | `reduz o centroide (d = −0,67) e a entropia (d = −0,62)` | `reduz o centroide (d = −0,67) e a entropia (d = −0,63)` |
| 15 | Seção 5.4, "Comparação com o piezo" | `o que indica que esse efeito é uma característica do sinal, e não do sensor.` | `o que indica que esse efeito é uma característica do sinal, e não do sensor; a seção 4.4 mostra que ele acompanha a tensão da bateria, e por isso não o atribuímos ao defeito.` |
| 16 | Seção 5.4, "Conclusão" | `como aumento da energia na banda de 335–500 Hz e como um leve deslocamento dos picos para frequências menores, mas com intensidade diferente` | `como aumento da energia na banda de 335–500 Hz, mas com intensidade diferente` |

Depois da troca 3, execute a célula do gráfico da seção 2.1 para o título novo aparecer na figura.

## Overleaf

| # | Onde | Trecho atual | Trocar por |
|---|---|---|---|
| 1 | Fig. 1, legenda | a frase final: Imagem original do notebook; o título ainda diz "filtrado", mas o código usa os sinais brutos, sem filtro. | (apagar a frase) |
| 2 | Seção II, "Mais vibração nem sempre significa falha" | `0,25 em F2 e 0,19 em F3` | `0,25 em F2 e 0,20 em F3` |
| 3 | Tabela da IMU, linha x | `$x$ & 2,267 & 2,536 & 280,7 & 290,2 & 0,58` | `$x$ & 2,267 & 2,536 & 280,6 & 289,1 & 0,58` |
| 4 | Tabela da IMU, linha y | `$y$ & 1,964 & 2,666 & 272,9 & 242,0 & 1,21` | `$y$ & 1,964 & 2,666 & 272,9 & 241,8 & 1,21` |
| 5 | Tabela da IMU, linha z | `$z$ & 5,502 & 7,295 & 319,8 & 346,3 & 1,42` | `$z$ & 5,502 & 7,295 & 319,8 & 346,1 & 1,42` |

Envie também `01_notebook_tempo.png` (nesta pasta) para `figuras/`, no lugar da atual: é o mesmo gráfico da seção 2.1 com o título corrigido. A cópia local do relatório com tudo aplicado compila em 6 páginas, sem erros; `relatorio/Projeto_Sinais_26_2.pdf` é essa compilação.

Os valores novos da tabela da IMU vêm das saídas da seção 5.2 do Colab executado do zero em 23/11/2026 às 22:04.

## O que ficou de fora

- **Trechos quase planos no piezo (seção 1.3):** o sinal tem trechos de cerca de 3 ms que se repetem em intervalos múltiplos de 16,7 ms nos 12 registros de SP3/C1, e o espaçamento coincide com os picos separados por 60 Hz comentados na seção 3. Vale uma frase na verificação dos dados, mas exige uma célula nova e a origem não pode ser afirmada; não foi aplicado.
- **Bandas preliminares da seção 3.3:** as primeiras células usam três bandas e são redefinidas logo depois. O relatório já explica isso, então ficaram como estão.
