# Utilização de Dados Abertos da ANTAQ para Análise Técnica

Encontro interno da **Superintendência de Fiscalização e Coordenação das Unidades
Regionais (SFC)** da ANTAQ, com as gerências da sede e as Gerências e Unidades Regionais.

Apresentação conjunta de duas gerências da SFC:

- **Pedro Henrique Soares** - Gerência de Planejamento e Inteligência da Fiscalização (GPF)
- **Fábio Queiroz Fonseca** - Gerência de Recursos e de Apoio Técnico (GRAT)

🔗 **Página publicada:** https://antaq.github.io/apresentacao_dados_abertos/

📦 **Repositório:** https://github.com/antaq/apresentacao_dados_abertos

> Este deck é a continuação de **"IA no dia a dia da Fiscalização"**, apresentada à SFC em
> 21 de setembro de 2026 (`antaq.github.io/apresentacao_ia_sfc`). Os slides 6 a 14 eram o
> bloco 4 daquele material, que ganhou apresentação própria. O slide 2 recapitula, em dois
> minutos, o que foi dito no dia anterior, para que quem não esteve lá acompanhe sem perda,
> e os slides 3 e 4 retomam o campo de instrução, que é a técnica de maior retorno daquele
> encontro.

## Sobre

- **Subtítulo:** como a ferramenta alcança o dado oficial da Agência, o que ela acha em segundos, e o que o dado não diz
- **Duração prevista:** 33 minutos (6 de abertura, 24 de exposição e demonstração no bloco 1, conforme o chip de tempo da divisória, e o restante em perguntas)
- **Plateia:** toda a SFC - gerências da sede (GCOR, GPF, GRAT) e Gerências e Unidades Regionais
- **Data:** 22 de setembro de 2026, às 10h20
- **Formato:** 16 slides em sequência única, em HTML 1920×1080

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
| 1 a 4 | Abertura, recapitulação e campo de instrução | 6 min |
| 5 a 15 | Bloco 1 · Cinco perguntas e uma ao vivo | 24 min |
| 16 | Encerramento | perguntas |

## O campo de instrução

Os **slides 3 e 4** são a ponte entre o encontro de ontem e o bloco de hoje, e os dois
mostram texto pronto para copiar, sem aspas ao redor:

- o **slide 3**, trazido do deck de IA, resolve o "não sei o que escrever nas instruções":
  em vez de a pessoa escrever, a ferramenta a entrevista e propõe a primeira versão;
- o **slide 4** mostra as instruções da conta do apresentador, em Configurações > Conta,
  que valem para toda conversa. É um exemplo de uso, não recomendação da Agência.

## A declaração antes do conector

O **slide 7** vem antes de o conector ser anunciado, de propósito: primeiro se diz por que
dado aberto importa, depois se diz o que é a ferramenta. Ele não traz número. Traz a
provocação ("dado público que ninguém consegue usar é transparência no papel"), a linha
de atrito (baixar a base, limpar, cruzar, conferir) e o fecho: transparência ativa se mede
em esforço, e hoje o esforço é uma pergunta.

## Os cinco casos

| Slide | Caso | O que ele mostra |
|---|---|---|
| 9 | Contratos que vencem | Onze contratos vencem entre hoje e 31 de dezembro, em dez portos, dois deles arrendamentos |
| 10 | A empresa pelo CNPJ | Outorgas, frota e fiscalizações de um CNPJ em uma pergunta, e o campo de vigência que mente |
| 11 | O que a Diretoria decide | Acórdãos que citam sobre-estadia passam de 14 para 72 por ano, e o que eles determinam à SFC |
| 12 | O teto da tarifa | A forma genérica devolve onze tetos; a específica devolve um, e a peça se instrui pela tabela homologada |
| 13 | A carteira da unidade | As 22 unidades lado a lado, e por que a maior carteira não é a de maior valor |

Os cinco seguem o mesmo molde: a pergunta como se digita, a resposta com número e fonte,
e a armadilha que o dado esconde. Nenhum deles traz a armadilha em tela: ela é dita em voz
alta, e está escrita na nota do apresentador de cada slide.

## A demonstração ao vivo

O **slide 14** é o único que depende da rede. Ele projeta a pergunta a ser colada, sem
aspas, para copiar e colar (`Preciso de um panorama, em PDF, sobre os autos de infração
lavrados sobre o art. 34 da Resolução 62/2021`), os números que a consulta deve devolver (44 linhas julgadas, 42
processos distintos, 6 terminando em multa) e o passo a passo para reproduzir. Se a rede
cair, o slide se narra sozinho: os números projetados são os mesmos que a consulta devolve.

O **slide 15** fecha o bloco com quatro perguntas reais, com porto, município e número de
infração escritos em tela, para a plateia copiar e trocar só o nome.

## Arquivos

| Arquivo | Conteúdo |
|---|---|
| [`index.html`](index.html) | Navegador dos slides (escala, teclado, notas, progresso) |
| `slide-01.html` … `slide-16.html` | Os 16 slides |
| [`KIT.md`](KIT.md) | Sistema visual (paleta, tipografia, componentes, mapa dos slides) |
| `Imagens/og-capa.jpg` | Cartão 1200x630 que aparece ao compartilhar o endereço |
| `Imagens/og-fonte.html` | Página que gera o cartão. Não faz parte da apresentação |
| [`notas-apresentador.md`](notas-apresentador.md) | Roteiro falado por slide, para impressão |
| [`PENDENCIAS.md`](PENDENCIAS.md) | O que foi resolvido, o que sobrou e as divergências registradas |

## Antes de apresentar

O conector é **projeto pessoal do apresentador**, com recurso próprio e sem fins lucrativos,
sobre dados que a ANTAQ publica. Não foi contratado, desenvolvido nem homologado pela
Agência, e o slide 8 declara isso em tela. A seção 5 do [`KIT.md`](KIT.md) traz a regra de
escrita que mantém essa distinção em todo texto projetado.

O endereço está projetado nos slides 8 e 16:
**`https://antaq.dadosabertos.dev/mcp`**. Atende por MCP e serve a qualquer
ferramenta compatível. Confirme que ele responde da máquina e da rede onde a apresentação
vai rodar, porque a sala vai tentar. Se o endereço mudar, os dois slides mudam juntos, e a
seção 5 do [`KIT.md`](KIT.md) registra o que precisa ser trocado.

Leia o [`PENDENCIAS.md`](PENDENCIAS.md). Os números do deck foram lidos do conector em
**22/09/2026**, sobre a captura dos painéis da madrugada do mesmo dia; se a data da
apresentação escorregar, reconfira, porque os painéis são recapturados. Os atos publicados
do slide 11 vêm de um acervo copiado até **27/08/2026**, que é o teto daquela contagem.

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
