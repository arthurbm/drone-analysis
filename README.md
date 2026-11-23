# Análise de sinais de vibração de drones

Projeto da disciplina CIN0020 — Sinais e Sistemas (2026.2, CIn/UFPE). Analisamos sinais de aceleração do dataset DronePropB nos domínios do tempo e da frequência para comparar hélices saudáveis e danificadas.

Equipe: Ana Maria Cunha, Mateus Ferreira Borges e Arthur Britto.

## Conteúdo

| Caminho | O que é |
|---|---|
| `ProjetoSinaisESistemas.ipynb` | Notebook completo da 1ª entrega (seções 1 a 5), com código, gráficos e interpretações |
| `secao4_celulas.ipynb` | Só as células da seção 4, já executadas, para copiar para o Colab compartilhado |
| `relatorio/` | Relatório em LaTeX (modelo IEEE) e o trecho da seção 4 (`secao4_comparacao_dominios.tex`) |
| `GLOSSARY.md` | Vocabulário do projeto: o que significa cada termo usado no notebook e no relatório |
| `Projeto Sinais e Sistemas 2026.2.pdf` | Enunciado oficial |
| `Projeto de Sinais e Sistemas 2026.2.pdf` | Slides de apresentação do projeto |

## Como executar

**No Google Colab (recomendado):** abra `ProjetoSinaisESistemas.ipynb` no Colab e use *Ambiente de execução → Executar tudo*. A primeira célula baixa o dataset (≈ 500 MB) com `gdown` e o descompacta em `/content/dados/`. O notebook não precisa de GPU.

**Localmente:** os caminhos do notebook apontam para `/content/`, que é a pasta do Colab. Para rodar fora dele, instale as dependências, baixe o dataset e ajuste os dois caminhos da primeira célula e o padrão de busca da célula de exploração (`/content/dados/**/*.mat`).

```bash
pip install -r requirements.txt
```

## Dataset

DronePropB — Ground Testing Dataset for Commercial Drones with Defective Propellers (Mendeley Data, DOI [10.17632/xkvfjmm8zg.1](https://doi.org/10.17632/xkvfjmm8zg.1), CC BY 4.0). O arquivo zip não é versionado neste repositório.

Registros usados (sensor piezoelétrico `AccData`, 10 kHz, 60 s cada):

- **Análise principal (SP3/C1):** `F0_SV0_SP3_C1_R1`, `R2`, `R3` (saudáveis) e `F{1,2,3}_SV{1,2,3}_SP3_C1` (nove danificados).
- **Investigação adicional:** os mesmos 12 registros, com os três eixos da IMU (`IMUData`, 1 kHz).
- **Verificação da bateria (seção 4.4):** `F{1,2,3}_SV{1,2,3}_SP3_C2`, usados somente para comparar a frequência do pico com a tensão da bateria.

## Entregas

- **1ª entrega:** seleção e preparação dos dados, análise no tempo e na frequência, comparação dos domínios e investigação adicional (seções 1 a 5 do notebook).
- **2ª entrega (02/12/2026):** classificação saudável × danificada com três modelos do mesmo algoritmo (características temporais, espectrais e combinadas), com divisão de treino e teste por registro.
