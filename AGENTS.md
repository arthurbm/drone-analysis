# drone-analysis

Projeto de CIN0020 (Sinais e Sistemas, CIn/UFPE): análise de vibração de drones do dataset DronePropB, comparando hélice saudável e danificada nos domínios do tempo e da frequência. Notebook, relatório e mensagens são escritos em português do Brasil.

## Fontes de verdade

- **Notebook:** o Google Colab compartilhado do grupo é o oficial; `analise_vibracao_drones.ipynb` é uma cópia. Toda mudança no notebook sai daqui como **repasse**.
- **Relatório:** o Overleaf do grupo é o oficial; `relatorio/overleaf/` é uma cópia. Mudança no relatório também sai como repasse.
- **Requisitos:** `docs/enunciado/enunciado.pdf` decide o que é exigido em cada entrega; `slides.pdf` é o resumo dado em aula.
- **Vocabulário:** `GLOSSARY.md`. Os termos de lá valem para notebook, relatório e mensagens.

## Repasses

Um **repasse** é um pacote pronto para colar no Colab ou no Overleaf. Cada um fica em `repasses/<assunto>/`. Leia `repasses/README.md` antes de criar ou alterar um repasse.

## Workspace local

`workspace/` é um repositório git próprio, só local, ignorado por este. É o lugar das conversas do grupo (têm telefones e e-mails), dos rascunhos de mensagens e dos scripts de exploração. Tudo que tiver dado pessoal ou for coordenação informal fica lá, com commit no git de `workspace/`.

## Ao analisar os sinais

- Células novas rodam sobre os mesmos registros do notebook antes de virarem repasse; `workspace/exploracao/secao4/` tem o gerador e o harness que recriam o estado do notebook até a seção 3.
- A posição dos picos do espectro acompanha a tensão da bateria (seção 4.4 do notebook). Descreva diferenças de posição de pico entre condições sempre ao lado da tensão da bateria.
- Afirme a causa física de um pico só com evidência nos dados; o dataset deixa sem documentação a rotação dos motores, o código C e a unidade do piezo.

## Agent skills

### Issue tracker

Issues are tracked in GitHub Issues for `arthurbm/drone-analysis` (via the `gh` CLI). See `docs/agents/issue-tracker.md`.

### Triage labels

Uses the five default triage labels as-is (`needs-triage`, `needs-info`, `ready-for-agent`, `ready-for-human`, `wontfix`). See `docs/agents/triage-labels.md`.

### Domain docs

Single-context: one `GLOSSARY.md` and `docs/adr/` at the repo root. See `docs/agents/domain.md`.
