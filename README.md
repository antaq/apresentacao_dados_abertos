# Utilização de Dados Abertos da ANTAQ para Análise Técnica

Encontro interno da **Superintendência de Fiscalização e Coordenação das Unidades
Regionais (SFC)** da ANTAQ, com as gerências da sede e as Gerências e Unidades Regionais.

Apresentação conjunta de duas gerências da SFC:

- **Pedro Henrique Soares** - Gerência de Planejamento e Inteligência da Fiscalização (GPF)
- **Fábio Queiroz Fonseca** - Gerência de Recursos e de Apoio Técnico (GRAT)

🔗 **Página publicada:** https://antaq.github.io/apresentacao_dados_abertos/

📦 **Repositório:** https://github.com/antaq/apresentacao_dados_abertos

> Este deck é a continuação de **"IA no dia a dia da Fiscalização"**, apresentada à SFC em
> 21 de setembro de 2026 (`antaq.github.io/apresentacao_ia_sfc`). Os slides 4 a 12 eram o
> bloco 4 daquele material, que ganhou apresentação própria. O slide 2 recapitula, em dois
> minutos, o que foi dito no dia anterior, para que quem não esteve lá acompanhe sem perda.

## Sobre

- **Subtítulo:** como a ferramenta alcança o dado oficial da Agência, o que ela acha em segundos, e o que o dado não diz
- **Duração prevista:** 30 minutos (18 de exposição, conforme o chip de tempo da divisória, e o restante em demonstração ao vivo e perguntas)
- **Plateia:** toda a SFC - gerências da sede (GCOR, GPF, GRAT) e Gerências e Unidades Regionais
- **Data:** 22 de setembro de 2026, às 10h20
- **Formato:** 13 slides em sequência única, em HTML 1920×1080

## Como usar

Abra o [`index.html`](index.html). Cada slide é um arquivo `slide-NN.html` autossuficiente,
carregado em um `<iframe>` e escalado para a tela.

| Tecla | Ação |
|---|---|
| `→` `espaço` `PageDown` | Próximo slide |
| `←` `PageUp` | Slide anterior |
| `Home` / `End` | Primeiro / último slide |
| `F` | Tela cheia |
| `N` | Abre e fecha as **notas do apresentador** |

As notas do apresentador ficam em bloco oculto dentro de cada slide e **nunca aparecem na
projeção**: só no painel lateral do `index.html`. A barra inferior mostra o progresso por
bloco temático.

Para servir localmente:

```bash
python3 -m http.server 8130
```

## Blocos

| Slides | Bloco | Tempo |
|---|---|---|
| 1 a 2 | Abertura e recapitulação | 3 min |
| 3 a 12 | Bloco 1 · Conector e dados abertos | 18 min |
| 13 | Encerramento | — |

## As quatro demonstrações

| Slide | Demonstração | O que ela mostra |
|---|---|---|
| 6 | O enquadramento genérico | Qual dispositivo mais soma multa, e por quê isso é um problema de redação |
| 8 | O histórico do fiscalizado | Autuações de uma empresa por unidade, infração e desfecho, em segundos |
| 9 | A citação que a base erra | O conector localiza o dispositivo e avisa onde o rótulo da base está errado |
| 10 | Dado aberto não é dado limpo | Multa de valor zero, linha que não é processo, e o número que não fecha |

A quarta é a mais importante do deck: ela é sobre o que o dado **não** diz.

## Arquivos

| Arquivo | Conteúdo |
|---|---|
| [`index.html`](index.html) | Navegador dos slides (escala, teclado, notas, progresso) |
| `slide-01.html` … `slide-13.html` | Os 13 slides |
| [`KIT.md`](KIT.md) | Sistema visual (paleta, tipografia, componentes, mapa dos slides) |
| `Imagens/og-capa.jpg` | Cartão 1200x630 que aparece ao compartilhar o endereço |
| `Imagens/og-fonte.html` | Página que gera o cartão. Não faz parte da apresentação |
| [`notas-apresentador.md`](notas-apresentador.md) | Roteiro falado por slide, para impressão |
| [`PENDENCIAS.md`](PENDENCIAS.md) | O que foi resolvido, o que sobrou e as divergências registradas |

## Antes de apresentar

Leia o [`PENDENCIAS.md`](PENDENCIAS.md). Os números do deck foram lidos do conector em
**16/09/2026**, sobre uma captura do painel de **18/08/2026**; se a data da apresentação
escorregar, reconfira, porque a base é atualizada.

## Publicação (GitHub Pages)

A página é servida pela branch `main`, na raiz do repositório, no mesmo padrão das demais
apresentações: em **Settings → Pages**, *Source* é **Deploy from a branch** → `main` →
`/ (root)`. O arquivo `.nojekyll` impede que o Jekyll ignore arquivos e pastas iniciados
por `_`.

A primeira compilação do Pages não dispara sozinha ao ligar a opção. Se a página ficar em
404, peça a compilação à mão:

```bash
gh api -X POST repos/antaq/apresentacao_dados_abertos/pages/builds
```

A partir daí, todo `push` na `main` republica a página automaticamente.

### Cartão de compartilhamento

O `index.html` traz as metaetiquetas Open Graph, e por isso o endereço colado no WhatsApp ou
no Teams abre com o cartão [`Imagens/og-capa.jpg`](https://antaq.github.io/apresentacao_dados_abertos/Imagens/og-capa.jpg) em vez do endereço cru.
Para trocar a arte, use `Imagens/og-fonte.html` e siga a seção 11 do [`KIT.md`](KIT.md).
O arquivo precisa continuar com **1200x630** e **abaixo de 300 KB**, senão a prévia não
aparece. A prévia fica em cache no aplicativo por alguns dias depois de publicada.
