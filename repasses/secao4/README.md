# Repasse: seção 4 (comparação dos domínios)

Atende ao item 3.4 do enunciado: comparação entre tempo e frequência nos mesmos registros, dois achados sustentados por gráficos e medidas, redundância entre características e conjunto proposto para a classificação.

## Colab

1. Abra `colab_celulas.ipynb` no Colab, selecione todas as células (Ctrl+Shift+A) e copie (Ctrl+C).
2. No notebook do grupo, na seção **4. Comparação entre os Domínios**, apague tudo o que está abaixo do título e antes da seção 5: o parágrafo "Juntamos as características…", a célula do ranking e as células vazias.
3. Cole as 16 células logo abaixo do título da seção 4 (Ctrl+V).
4. Use *Ambiente de execução → Executar tudo*. A seção 4 depende das seções 1 a 3 e define `cohen_d`, que a seção 5 usa.
5. Confira as saídas com as que estão gravadas em `colab_celulas.ipynb`. Dois números para checar rápido: d de Cohen do RMS = 0,30 com AUC = 0,51 (ranking), e r = 0,992 no título do gráfico da bateria.

A seção 4.4 lê também os nove registros danificados de SP3/C2, a partir da tabela `tabela` criada na seção 1. Eles servem só para a verificação da bateria.

## Overleaf

1. Envie `comparacao_dominios.png` para a pasta `figuras/` do projeto.
2. Substitua a seção "Comparação dos domínios e seleção de atributos" pelo conteúdo de `relatorio_secao4.tex`.
3. Compile. O trecho ocupa cerca de meia página de texto, uma tabela de uma coluna e uma figura de largura inteira (`figure*`).

O trecho ainda não foi compilado: confira a tabela e a posição da figura na primeira compilação.

## Arquivos

| Arquivo | Destino |
|---|---|
| `colab_celulas.ipynb` | Colab do grupo, seção 4 |
| `relatorio_secao4.tex` | Overleaf, seção de comparação dos domínios |
| `comparacao_dominios.png` | Overleaf, `figuras/`; é gerada pela última célula de código da seção 4.4 como `comp_dominios_relatorio.png` |
