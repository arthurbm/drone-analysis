# Repasse: seção 4 (comparação dos domínios)

Atende ao item 3.4 do enunciado: comparação entre tempo e frequência nos mesmos registros, dois achados sustentados por gráficos e medidas, redundância entre características e conjunto proposto para a classificação.

## Colab

1. Abra `colab_celulas.ipynb` no Colab, selecione todas as células (Ctrl+Shift+A) e copie (Ctrl+C).
2. No notebook do grupo, na seção **4. Comparação entre os Domínios**, apague tudo o que está abaixo do título e antes da seção 5: o parágrafo "Juntamos as características…", a célula do ranking e as células vazias.
3. Cole as 16 células logo abaixo do título da seção 4 (Ctrl+V).
4. Use *Ambiente de execução → Executar tudo*. A seção 4 depende das seções 1 a 3 e define `cohen_d`, que a seção 5 usa.
5. Confira as saídas com as que estão gravadas em `colab_celulas.ipynb`. Dois números para checar rápido: d de Cohen do RMS = 0,30 com AUC = 0,51 (ranking), e r = 0,992 no título do gráfico da tensão da bateria.

A seção 4.4 lê também os nove registros danificados de SP3/C2, a partir da tabela `tabela` criada na seção 1. Eles servem só para a verificação da tensão da bateria.

## Overleaf

1. Envie `09_notebook_comparacao.png` para a pasta `figuras/` do projeto.
2. Apague a linha `\section{Comparação entre os domínios}`, hoje sem conteúdo, e cole no lugar dela o conteúdo de `relatorio_secao4.tex`, que já traz o título da seção.
3. Faça os três ajustes abaixo em outras seções, para que o relatório não contradiga a seção nova.
4. Compile. O trecho ocupa quase duas colunas, cerca de uma página: uma coluna de texto e títulos, a Tabela `tab:comp` (cerca de 0,3 coluna) e a figura (cerca de 0,5 coluna).

Compilada localmente com pdfLaTeX, a cópia do relatório com o trecho e os três ajustes tem 6 páginas, sem erros, e a seção nova cabe inteira na página 5; `relatorio/Projeto_Sinais_26_2.pdf` é essa compilação. Confira o mesmo no Overleaf. Se lá faltar espaço, remova a Tabela `tab:comp` antes da figura, que é a que sustenta os dois achados; nesse caso, troque a frase "A Tabela~\ref{tab:comp} mostra o motivo:" por "O motivo é que" (os valores de $d$ citados no texto continuam valendo).

### Ajustes em outras seções

| Onde | Trecho atual | Trocar por |
|---|---|---|
| Seção I, "Dataset e recorte de comparação" | `e a tensão da bateria, que não é usada aqui.` | `e a tensão da bateria, usada apenas na verificação da Seção~\ref{sec:comp}.` |
| Seção III, "Picos e redistribuição" | `mesmo código SP não comprova a mesma RPM efetiva.` | `mesmo código SP não comprova a mesma RPM efetiva, e a Seção~\ref{sec:comp} mostra que ele acompanha a tensão da bateria.` |
| Conclusões | `A IMU confirma que a direção altera intensidade e distribuição espectral.` | `A comparação entre domínios mostra que janelas de mesma intensidade podem ter espectros distintos e que a posição dos picos acompanha a tensão da bateria, o que impede atribuir esse deslocamento ao defeito. A IMU confirma que a direção altera intensidade e distribuição espectral.` |

A cópia local `relatorio/overleaf/Projeto_Sinais_26_2/conference_101719.tex` já está com o trecho e os três ajustes aplicados, e serve de referência.

## Arquivos

| Arquivo | Destino |
|---|---|
| `colab_celulas.ipynb` | Colab do grupo, seção 4 |
| `relatorio_secao4.tex` | Overleaf, seção "Comparação entre os domínios" |
| `09_notebook_comparacao.png` | Overleaf, `figuras/`; é gerada pela última célula de código da seção 4.4 do notebook, com esse mesmo nome |
