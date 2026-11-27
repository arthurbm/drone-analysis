# Repasses

As versões oficiais do notebook e do relatório ficam no Google Colab e no Overleaf do grupo. Um **repasse** é o pacote que leva uma mudança feita neste repositório até lá: células prontas para colar no Colab, trecho em LaTeX para colar no Overleaf e as figuras que o trecho usa.

| Repasse | O que leva |
|---|---|
| [`secao4/`](secao4/) | Seção 4 do notebook e do relatório: comparação dos domínios, dois achados e conjunto de características para a classificação |
| [`ajustes-outras-secoes/`](ajustes-outras-secoes/) | Correções pontuais nas seções 1, 2, 3 e 5 do notebook e no relatório: frases que o achado da bateria contradiz, números defasados e acabamento |

## Formato

Cada repasse é uma pasta `repasses/<assunto>/` com:

- `README.md`: o que apagar e onde colar, no Colab e no Overleaf, e o que conferir depois;
- `colab_celulas.ipynb`: só as células novas, já executadas, para comparar as saídas depois de colar;
- `relatorio_<assunto>.tex`: o trecho do relatório, usando apenas pacotes e macros já presentes no preâmbulo;
- as figuras que o trecho usa, com o mesmo nome que terão na pasta `figuras/` do Overleaf.

As mesmas células e o mesmo trecho também são aplicados às cópias locais (`analise_vibracao_drones.ipynb` e `relatorio/overleaf/`), para que o repositório mostre o resultado completo.
