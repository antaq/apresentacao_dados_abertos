# Pendências da apresentação "Utilização de Dados Abertos da ANTAQ para Análise Técnica"

Situação em: **16/09/2026** · Apresentação marcada para **22/09/2026, às 10h20**

> Não há marcador `[CONFIRMAR]`, `[DATA]` ou `[CAPTURA]` em aberto no deck. O que continua
> pendente é **fora do HTML**: criar o repositório, publicar a página, e uma divergência de
> conteúdo que precisa de decisão antes de projetar (seção 3).

---

## 1. Publicação

| Item | Situação |
|---|---|
| **Repositório `antaq/apresentacao_dados_abertos`** | ⏳ Ainda não criado. O deck inteiro já aponta para esse endereço: linha de contato do slide 13, código de leitura óptica e README. |
| **GitHub Pages** | ⏳ Depende do repositório. Ligar em *Deploy from a branch* → `main` → `/ (root)` e, se a página ficar em 404, pedir a primeira compilação à mão com `gh api -X POST repos/antaq/apresentacao_dados_abertos/pages/builds`. Ela não dispara sozinha. |
| **Código de leitura óptica** | ✅ Gerado em 16/09/2026 e conferido por decodificação: aponta para `https://antaq.github.io/apresentacao_dados_abertos/`. Arquivos `Imagens/qr-material-apoio.svg` e `.png`. |

---

## 2. Depende do apresentador, e não está em tela nenhuma

| Slide | O que precisa ser dito em voz alta |
|---|---|
| **13** | A oferta de abrir o **conector de Dados Abertos** para quem quiser experimentar. Sem essa frase, a apresentação termina sem próximo passo. |
| **2** | Que quem não esteve no dia 21 não fica para trás, e que o material completo daquele dia está no endereço da linha de fonte. |

---

## 3. A conferir antes de projetar

| Onde | O quê |
|---|---|
| **Slides 5 e 9** | ⚠️ **Divergência aberta.** O slide 5 diz que o conector "consome apenas dado aberto oficial", e o chip fala em "acervo normativo publicado". Mas o acervo consultado pelo conector (50 documentos, 2.530 trechos, citado no slide 9) inclui **8 Manuais de Fiscalização e Ordens de Serviço da SFC**, que a própria apresentação de 21/09 classifica como documentos internos não publicados. Ou se retiram esses 8 do acervo, ou o slide 5 muda de redação. Não projetar antes de resolver. |
| **Slide 7** | O cartão de alerta é atribuído ao **curso de introdução à fiscalização da SFC**. Conferir a atribuição antes de dizer em voz alta de onde vem. |
| **Deck inteiro** | Todos os números foram lidos do conector de Dados Abertos em **16/09/2026**, sobre uma captura do painel de **18/08/2026**. Se a apresentação escorregar de data, reconferir: a base é atualizada. |
| **Demonstração ao vivo** | O conector `dados-antaq` precisa estar acessível na máquina da apresentação. Se a rede cair, o procedimento é narrar o que está projetado; os quatro slides de demonstração se sustentam sozinhos. |

---

## 4. Divergências registradas

1. **O deck nasceu de um bloco.** Os slides 4 a 12 eram o bloco 4 de "IA no dia a dia da
   Fiscalização" (21/09/2026) e foram movidos para cá sem mudança de conteúdo, só de
   numeração e de rodapé. Aquele deck ficou com 31 slides.
2. **A frase-âncora repete duas vezes, não três.** No deck de origem ela aparecia nos
   slides 7, 30 e 37. O slide 7 ficou lá; aqui ela aparece nos slides 5 e 12. As notas
   foram ajustadas para dizer "segunda e última vez", e para lembrar que a plateia do dia
   anterior já a ouviu.
3. **Recapitulação em vez de fundamentos.** O slide 2 condensa em quatro linhas o que o
   deck de origem gasta dois blocos inteiros para construir. Quem for apresentar precisa
   resistir à tentação de abrir cada item: o slide é ponte, não aula.
4. **Leiaute L7 (captura de tela) continua sem uso.** Nenhum slide traz captura; o conteúdo
   ocupa a largura cheia, com corpo maior. Decisão herdada.
5. **Travessão longo.** As regras proíbem travessão longo em todo texto do deck. Ele
   sobrevive em um lugar só: a dica de ferramenta dos pontinhos de progresso do
   `index.html`, que é interface de navegação e não texto projetado.
