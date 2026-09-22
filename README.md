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
| 3 a 12 | Bloco 1 · Quatro perguntas da rotina | 18 min |
| 13 | Encerramento | perguntas |

## Os quatro casos

| Slide | Caso | O que ele mostra |
|---|---|---|
| 6 | Contratos que vencem | Onze contratos de arrendamento e de adesão vencem até dezembro, em dez portos |
| 7 | A empresa antes da fiscalização | Outorgas, frota e fiscalizações de um CNPJ em uma pergunta, e o campo de vigência que mente |
| 8 | O que a Diretoria decide | Acórdãos que citam sobre-estadia passam de 14 para 72 por ano, e o que eles determinam à SFC |
| 9 | O tipo residual | O enquadramento genérico arquiva quase o dobro da média, e o número grande vem de uma empresa só |

Os quatro seguem o mesmo molde: a pergunta como se digita, a resposta com número e fonte,
e a armadilha que o dado esconde.

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

O conector é **projeto pessoal do apresentador**, com recurso próprio e sem fins lucrativos,
sobre dados que a ANTAQ publica. Não foi contratado, desenvolvido nem homologado pela
Agência, e o slide 5 declara isso em tela. A seção 5 do [`KIT.md`](KIT.md) traz a regra de
escrita que mantém essa distinção em todo texto projetado.

O endereço está projetado nos slides 5 e 13:
**`https://antaq.dadosabertos.dev/mcp`**. Atende por MCP e serve a qualquer
ferramenta compatível. Confirme que ele responde da máquina e da rede onde a apresentação
vai rodar, porque a sala vai tentar. Se o endereço mudar, os dois slides mudam juntos, e a
seção 5 do [`KIT.md`](KIT.md) registra o que precisa ser trocado.

Leia o [`PENDENCIAS.md`](PENDENCIAS.md). Os números do deck foram lidos do conector em
**21/09/2026**, sobre uma captura do painel de **18/08/2026**; se a data da apresentação
escorregar, reconfira, porque a base é atualizada. Os atos publicados vêm de um acervo
atualizado com o dia, e por isso os números do slide 8 mudam a cada consulta.

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
