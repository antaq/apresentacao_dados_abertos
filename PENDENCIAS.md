# Pendências da apresentação "Utilização de Dados Abertos da ANTAQ para Análise Técnica"

Situação em: **22/09/2026, manhã** · Apresentação marcada para **22/09/2026, às 10h20**

> Não há marcador `[CONFIRMAR]`, `[DATA]` ou `[CAPTURA]` em aberto no deck. A página já está
> publicada em **https://antaq.github.io/apresentacao_dados_abertos/**, e o código de leitura
> óptica do slide 13 aponta para ela. A reconferência dos números **foi feita em 22/09/2026**
> (seção 3) e o bloco central foi refeito pela segunda vez, com cinco casos em vez de quatro
> (seção 4, item 7). O que sobra é uma fala que não está em tela nenhuma (seção 2) e o
> acervo de atos publicados, que **não** foi atualizado e continua congelado em 27/08/2026.

---

## 1. Publicação

| Item | Situação |
|---|---|
| **Repositório `antaq/apresentacao_dados_abertos`** | ✅ Criado e publicado na `main` em 16/09/2026. |
| **GitHub Pages** | ✅ Ligado em *Deploy from a branch* → `main` → `/ (root)`. Como o Pages já estava ligado antes do primeiro `push`, a compilação disparou sozinha; se num próximo deck a página ficar em 404, o caminho é `gh api -X POST repos/<org>/<repo>/pages/builds`. Página no ar e conferida em 16/09/2026. |
| **Código de leitura óptica** | ✅ Gerado em 16/09/2026 e conferido por decodificação: aponta para `https://antaq.github.io/apresentacao_dados_abertos/`. Arquivos `Imagens/qr-material-apoio.svg` e `.png`. |

---

## 2. Depende do apresentador, e não está em tela nenhuma

| Slide | O que precisa ser dito em voz alta |
|---|---|
| **2** | Que quem não esteve no dia 21 não fica para trás, e que o material completo daquele dia está no endereço da linha de fonte. |

Resolvido em 21/09/2026: a oferta de montar a primeira consulta junto com a unidade que
pedir **passou a estar projetada**, na caixa azul-clara do slide 12. O deck não termina
mais sem próximo passo em tela.

---

## 3. A conferir antes de projetar

| Onde | O quê |
|---|---|
| **Slide 5** | O conector é **projeto pessoal do apresentador**, com recurso próprio e sem fins lucrativos, e o slide declara isso em tela, junto com as quatro fontes que ele consome. Confirmar que a declaração está redigida como você quer dizer em voz alta, porque ela é lida por colegas num evento oficial da Superintendência e é ela que separa o método da pessoa. |
| **Deck inteiro** | ✅ Reconferido em **22/09/2026**, sobre a captura dos painéis da madrugada do mesmo dia (Fiscalização 02:29, Administração Portuária 02:26, Estatístico Aquaviário 02:51, Portos Públicos 02:25). Os valores que mudaram foram trocados no slide: frota da empresa do caso 2 de 57 para **61**, campo de outorga de 3.169 para **3.185** linhas e de 1.350 para **1.362** extintas, e os arquivados sem irregularidade de 11.876 para **11.926** (slides 7 e 11). Os demais se mantiveram. Como a captura e a consulta são do mesmo dia, a **cláusula de captura saiu de todas as linhas de fonte**. |
| **Slide 8** | ⚠️ O acervo de atos publicados **não foi atualizado**: o conector responde `copiado_em: 2026-08-27`. A linha de fonte voltou a citar a cópia (`copiado até 27/08/2026`) e a faixa vermelha passou a dizer que a contagem de 2026 se encerra onde a cópia termina, porque sem isso o slide afirmaria algo falso. Se o acervo for recarregado antes das 10h20, refazer a busca por "sobre-estadia" em 2026 (hoje **42**) e o total de **21.091 atos**, e reavaliar se a data ainda precisa aparecer. |
| **Nomes de empresa** | Dois números do deck têm nome de empresa por trás que **não é projetado**: os onze contratos do caso 1 (slide 6) e a carteira por unidade do caso 5 (slide 10), em que o maior autuado não aparece. Se a sala perguntar, a resposta vem da consulta ao vivo, não do slide. |
| **Slide 10** | A soma de processos distintos por unidade dá **17.568**, um a mais do que os **17.567** distintos da base inteira: há um processo registrado em duas unidades. O slide projeta só o total da base, e por isso a coluna não é somável em tela. |
| **Demonstração ao vivo** | O conector `dados-antaq` atende em `https://antaq.dadosabertos.dev/mcp` e precisa estar acessível da máquina da apresentação, inclusive pela rede da Agência. Confirmar isso antes de subir ao palco, porque o endereço está projetado nos slides 5 e 13 e a sala vai tentar. Se a rede cair, o procedimento é narrar o que está projetado; os cinco slides de demonstração se sustentam sozinhos. |

---

## 4. Divergências registradas

> **Resolvido em 21/09/2026: a divergência do acervo.** Os **Manuais de Fiscalização e as
> Ordens de Serviço da SFC saíram do acervo consultado pelo conector**. Com isso ele passa a
> consumir apenas documento publicado, e o slide 5 pôde nomear as fontes em tela: painéis
> públicos da ANTAQ, painéis do ONTL, Comex Stat do MDIC e atos e normas publicados. O
> bloqueio que impedia projetar os slides 5 e 13 com o endereço deixou de existir.


> **Correção de 21/09/2026, e é a mais sensível deste deck.** Até esta data o deck
> apresentava o conector como produto institucional: o slide 5 se chamava "O conector de
> dados abertos da ANTAQ foi feito aqui", dizia "feito dentro da própria Superintendência,
> sem custo de contratação", e cinco linhas de fonte o atribuíam à GPF. Estava errado. O
> conector é **projeto pessoal do apresentador**, com recurso próprio, sem fins lucrativos,
> usando dados que a ANTAQ publica. O slide 5 virou declaração de interesse, as linhas de
> fonte passaram a dizer "via conector MCP independente", e a regra de escrita está na
> seção 5 do KIT.
>
> **O que isso reabriu, e como terminou.** A correção tornou a divergência do acervo mais
> grave do que uma imprecisão de redação: documentos que a apresentação de 21/09 classifica
> como internos estariam num serviço particular, hospedado fora da Agência, cujo endereço
> este deck projeta. Não era problema de texto, e a resposta não foi ajustar o texto: os
> documentos internos saíram do acervo do conector no mesmo dia, como registra o quadro
> acima.

1. **O deck nasceu de um bloco.** Os slides 4 a 12 vieram do bloco 4 de "IA no dia a dia da
   Fiscalização" (21/09/2026), primeiro só com troca de numeração e de rodapé. O conteúdo
   do bloco central foi refeito depois, no mesmo dia (item 6). Aquele deck ficou com 31
   slides.
2. **A frase-âncora repete duas vezes, não três.** No deck de origem ela aparecia nos
   slides 7, 30 e 37. O slide 7 ficou lá; aqui ela aparece nos slides 5 e 12. As notas
   foram ajustadas para dizer "segunda e última vez", e para lembrar que a plateia do dia
   anterior já a ouviu.
3. **Recapitulação em vez de fundamentos.** O slide 2 condensa em quatro linhas o que o
   deck de origem gasta dois blocos inteiros para construir. Quem for apresentar precisa
   resistir à tentação de abrir cada item: o slide é ponte, não aula.
4. **Leiaute L7 (captura de tela) continua sem uso.** Nenhum slide traz captura; o conteúdo
   ocupa a largura cheia, com corpo maior. Decisão herdada.
5. **Travessão longo: resolvido em 21/09/2026.** Ele sobrevivia na dica de ferramenta dos
   pontinhos de progresso do `index.html`, sob o argumento de que interface não é texto
   projetado. O argumento caiu: a regra não tem exceção. A dica passou a usar ` · `, e não
   há travessão longo nem meia-risca em nenhum arquivo do repositório.
6. **O bloco central foi refeito em 21/09/2026.** As quatro demonstrações herdadas do deck
   de origem saíram e deram lugar a **quatro perguntas da rotina da fiscalização** (slides 6
   a 9), cada uma no mesmo molde: a pergunta como se digita, a resposta com número e fonte,
   e a armadilha que o dado esconde. O slide 10 consolidou a cautela em cinco perguntas, e o
   slide 12 passou a projetar o próximo passo. Motivo da troca: as demonstrações antigas
   mostravam defeito do dado sem responder pergunta de trabalho, e uma delas afirmava, sobre
   nulidade por enquadramento genérico, o que o próprio dado não sustenta.
7. **Os slides 9 e 10 foram refeitos em 22/09/2026, e o bloco passou a ter cinco casos.** O
   slide 9 era uma estatística do inciso residual que terminava sem ação, e o slide 10 era
   uma lista de cautelas, não um caso. Nenhum dos dois cabia no molde do bloco. No lugar
   entraram dois casos de trabalho: **o teto da tarifa** (slide 9), em que a forma genérica
   devolve onze valores e a específica devolve um, e **a carteira da unidade** (slide 10),
   com as 22 unidades lado a lado. As cinco cautelas do slide 10 antigo não se perderam:
   cada uma já aparece como armadilha dentro do caso a que pertence. A troca obrigou a
   renomear o bloco de quatro para cinco perguntas nos slides 1 e 3, no `index.html`, no
   README e no KIT.
8. **O slide 5 foi reorganizado em 22/09/2026.** Os quatro cartões tinham borda e ênfase
   diferentes entre si e a hierarquia do slide estava invertida: a frase-âncora, que é
   lembrete do dia anterior, era o elemento mais alto do slide, e o endereço do conector
   vinha em caixa clara. Os cartões passaram a ter o mesmo tratamento, o **endereço virou a
   âncora visual** (faixa escura com tarja dourada, URL em 48px) e a frase desceu para uma
   linha discreta, porque ela volta inteira no slide 12.
