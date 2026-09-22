# KIT DE DESIGN · "Dados Abertos da ANTAQ para análise técnica" (SFC · ANTAQ)

Sistema visual EXATO desta apresentação. Deriva do KIT da Trilha Técnica (modelo SisPAT).
**Referência de ouro:** `../GPFTrilhaTecnico/apresentacao/` (KIT.md + slide-01, 04, 20, 29, 61).
Onde a especificação de conteúdo divergir deste KIT, **prevalece o KIT**.

Total de arquivos: **16**: `slide-01.html` a `slide-16.html`, em sequência única.
Não há slides de reserva.

Este deck nasceu do bloco 4 da apresentação "IA no dia a dia da Fiscalização"
(21/09/2026), que virou apresentação própria. Boa parte dos slides 5 a 16 vem de lá,
renumerada; a coluna "Vinha de" do mapa em 9 diz de onde saiu cada um. O slide 3 é o
slide 28 daquele deck, trazido inteiro. Os slides 1, 2, 4, 10, 11, 12 e 14 são novos.

Cada slide é um arquivo HTML autossuficiente 1920×1080 (16:9), carregado em `<iframe>`
pelo `index.html`, que escala para a tela e navega por `postMessage`.

---

## 1. REGRAS DURAS (não negociáveis)

1. HTML completo e autossuficiente (`<!DOCTYPE html>` … `</html>`).
2. Base de leiaute **1920×1080**. `html { font-size: 26px; }`.
3. CDNs exatamente como no boilerplate da seção 3.
4. Montserrat = títulos/rótulos. Open Sans = corpo.
5. **NUNCA** gerar barra de rolagem. Nada pode estourar 1080px de altura nem 1920px de
   largura. `body { overflow:hidden }` e `.slide-container { overflow:hidden }`.
   Na dúvida, **menos texto e mais respiro**.
6. Os **dois últimos elementos antes de `</body>`** são, nesta ordem:
   (a) o script de notas do apresentador (seção 7) e (b) o script de navegação (seção 8).
7. Imagens em `Imagens/` (caminho relativo). Disponíveis: `logo-antaq-branca.png`,
   `logo-antaq-azul.png`, `favicon-16.png`, `favicon-32.png`, `apple-touch-icon.png`,
   `og-capa.jpg` e a fonte dela, `og-fonte.html` (seção 11).
   **Não há capturas de tela.** Todo slide se sustenta em tipografia, cor e diagrama.
8. Idioma pt-BR.

## 1.1 REGRAS DE ESCRITA (valem para todo texto visível)

- Português formal da administração pública. Frases curtas.
- **Proibido o travessão longo (U+2014) e o traço médio (U+2013) em texto corrido.** Use hífen
  simples `-` ou parênteses. (O separador `·` é permitido em rodapés e rótulos.)
- **Sem estrangeirismos**: "instrução" (não *prompt*), "conector" (não *plugin*),
  "conta" (não *account*), "programa" (não *software*). Exceções consagradas: *prompt*
  apenas ao citar guia da SGD/MGI, e *MCP* (nome próprio de protocolo).
- **Máximo de 6 linhas de texto** por slide (não conta título, rodapé nem tabela).
- **Não inventar nada.** Todo número, data, valor e norma vem da especificação.
  Faltou informação, deixe marcador `[CONFIRMAR ...]` **visível** (seção 6).
- Neutralidade de fornecedor: nenhuma marca de produto de IA é citada. Legenda de
  qualquer tela de ferramenta reproduzida: "demonstração em uma das ferramentas
  disponíveis no mercado".
- **Todo número exibido tem fonte identificada no rodapé do slide** (seção 5.4).

---

## 2. PALETA

| Token | Hex | Uso |
|---|---|---|
| Azul institucional | `#003366` | Títulos, barras, cabeçalho de tabela |
| Azul vibrante | `#0066CC` | Acentos, ícones, destaques |
| Dourado | `#FFD700` | Acento em capa, divisórias, encerramento, faixa-âncora |
| Fundo claro | `#ffffff` / `#f3f4f6` | Slides de conteúdo |
| Cartão claro | `#F8FAFC` | Cartões |
| Cartão azul claro | `#F0F9FF` + borda `#BAE6FD` | Caixas de destaque |
| Texto corpo | `#374151` / `#4B5563` | Parágrafos |
| Texto suave | `#6B7280` / `#9CA3AF` | Legendas e rodapé |
| Proibição | `#FEE2E2` / borda `#DC2626` / texto `#991B1B` | Vetos do slide 16. **Não é mais usado para armadilha** (ver 6.6) |
| Marcador pendente | `#FEF3C7` / borda tracejada `#D97706` / texto `#92400E` | (não há marcador em aberto no deck) |

Gradiente escuro (capa, divisórias, frases de impacto, encerramento):
`linear-gradient(135deg, #002244 0%, #003366 50%, #004488 100%)`

---

## 3. BOILERPLATE `<head>` (idêntico em TODO slide)

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="utf-8"/>
<meta content="width=device-width, initial-scale=1.0" name="viewport"/>
<title>TÍTULO DO SLIDE</title>
<link rel="icon" href="favicon.ico" sizes="any"/>
<link rel="icon" type="image/png" sizes="32x32" href="Imagens/favicon-32.png"/>
<link rel="icon" type="image/png" sizes="16x16" href="Imagens/favicon-16.png"/>
<link rel="apple-touch-icon" href="Imagens/apple-touch-icon.png"/>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800;900&family=Open+Sans:wght@400;500;600;700&display=swap" rel="stylesheet"/>
<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet"/>
<style>
  html { font-size: 26px; }
  body { margin:0; padding:0; background-color:#f3f4f6; overflow:hidden; font-family:'Open Sans', sans-serif; }
  .slide-container { width:100vw; height:100vh; position:relative; display:flex; flex-direction:column; background-color:#ffffff; overflow:hidden; }
  .font-montserrat { font-family:'Montserrat', sans-serif; }
  .text-brand-primary { color:#003366; } .bg-brand-primary { background-color:#003366; }
  .text-brand-secondary { color:#0066CC; } .bg-brand-secondary { background-color:#0066CC; }
  /* … estilos específicos do slide … */
</style>
</head>
```

---

## 4. ESCALA TIPOGRÁFICA MÍNIMA (plateia presencial)

Projeção em sala. **Legibilidade vence efeito.** Use `px` explícito, não classes de
tamanho do Tailwind, para tudo que for texto de conteúdo.

| Elemento | Tamanho | Peso |
|---|---|---|
| Título de slide de conteúdo (H1) | 44 a 52px | 700 Montserrat, caixa alta |
| Subtítulo do header | 26 a 30px | 500 Open Sans, `#6B7280` |
| Item de lista (texto principal) | **30 a 36px** | 600 |
| Texto de apoio / descrição de item | **24 a 28px** | 400 |
| Célula de tabela | **24 a 28px** | 400/600 |
| Cabeçalho de tabela | 22 a 24px | 700 Montserrat, caixa alta |
| Rótulo de coluna comparativa | 26 a 30px | 700 Montserrat, caixa alta |
| Frase de impacto (L2) | **56 a 84px** | 800/900 Montserrat |
| Destaque numérico (L8) | 120 a 190px | 900 Montserrat |
| Bloco monoespaçado (L6) | 20 a 23px | 400, `line-height:1.5` |
| Rodapé | 17 a 19px | 500 |
| Legenda / linha de fonte | 17 a 21px | 400, itálico quando for ressalva |

**Piso absoluto: nenhum texto abaixo de 17px.** Nada de `text-xs`/`text-sm` do Tailwind
em conteúdo (só no rodapé, e ainda assim com `px` explícito).

---

## 5. SLIDE DE CONTEÚDO (fundo branco): estrutura padrão

```html
<body>
<div class="slide-container">
  <div style="height:12px;background:#003366;width:100%;"></div>
  <div style="height:6px;background:#0066CC;width:100%;"></div>

  <!-- Header -->
  <div class="flex items-center justify-between px-16 pt-9 pb-3 z-10">
    <div>
      <div class="flex items-center gap-3 mb-1">
        <div class="w-1.5 h-9 bg-brand-secondary"></div>
        <h1 class="font-montserrat font-bold text-brand-primary uppercase tracking-tight" style="font-size:48px;line-height:1.1;">TÍTULO DO SLIDE</h1>
      </div>
      <p class="text-gray-500 font-medium ml-4" style="font-size:27px;">Subtítulo opcional</p>
    </div>
    <div class="flex items-center gap-3 opacity-80 text-brand-secondary flex-shrink-0 ml-8">
      <i class="fas fa-ICONE" style="font-size:26px;"></i>
      <p class="font-montserrat font-bold text-gray-400 tracking-widest" style="font-size:19px;">TAG DO BLOCO</p>
    </div>
  </div>

  <!-- Conteúdo -->
  <div class="flex-1 flex flex-col justify-center px-16 pb-6 z-10 min-h-0">
    <!-- … -->
  </div>

  <!-- Rodapé -->
  <div class="px-16 pb-6 flex justify-between items-end z-10">
    <div>
      <p class="text-gray-400 font-montserrat" style="font-size:18px;">Dados Abertos da ANTAQ para análise técnica · SFC · ANTAQ</p>
      <!-- linha de fonte, quando o slide exibir números (ver 5.4) -->
    </div>
    <p class="text-gray-300 font-mono" style="font-size:18px;">NN / 16</p>
  </div>
</div>
```

Se o título for longo, reduza para 44px em vez de quebrar o leiaute.

### 5.1 Tag do bloco (canto superior direito)

| Slides | Tag | Ícone |
|---|---|---|
| 2 | `ABERTURA` | `fa-clock-rotate-left` |
| 6 a 12, 14 e 15 | `DADOS ABERTOS` | `fa-plug` |

Slides sem tag: 1, 3, 4, 5, 13 e 16 (capa, os dois de campo de instrução, divisória,
frase L2 e encerramento).

### 5.2 Numeração no rodapé

- Slides 2 a 16: `NN / 16` (sem zero à esquerda; use `7 / 16`, `12 / 16`).
- Capa (slide 1): sem numeração.

### 5.3 Rodapé de slides escuros

Mesmo conteúdo, cores `color:#BFDBFE; opacity:.75`.

### 5.4 Linha de fonte (obrigatória quando o slide exibe número)

Logo abaixo do texto-base do rodapé, em 17px, `#9CA3AF`:

```html
<p class="text-gray-400" style="font-size:17px;">Fonte: TEXTO DA FONTE</p>
```

Fontes canônicas desta apresentação (use exatamente). Os números foram lidos em
**22 de setembro de 2026**, sobre a captura dos painéis da madrugada do mesmo dia. Como as
duas datas coincidem, **a linha de fonte não repete a data de captura**: basta a data da
consulta. A exceção é o acervo de atos publicados, que é cópia manual e está congelado em
**27/08/2026**: ali a data de cópia entra na linha de fonte, porque ela é o teto da contagem.

- Movimentação portuária (slide 6):
  `Fonte: painel Estatístico Aquaviário da ANTAQ, quadro de movimentação portuária por tipo de navegação, via conector MCP independente, em 22 de setembro de 2026.`
- Contratos de porto público (slide 8):
  `Fonte: painel Portos Públicos da ANTAQ, quadro "Portos Públicos" (559 contratos), via conector MCP independente, em 22 de setembro de 2026. Vencimento pela data de expiração do último instrumento.`
- Outorgas, frota e fiscalização por CNPJ (slide 9):
  `Fonte: painéis Outorgas de Navegação (quadros de outorgas e de frota) e Fiscalização da ANTAQ, via conector MCP independente, em 22 de setembro de 2026. Vigência pela data de extinção.`
- Atos publicados (slide 10), única linha que leva data de cópia:
  `Fonte: atos publicados pela ANTAQ (acervo da Biblioteca, copiado até 27/08/2026), espécie Acórdão, busca por "sobre-estadia" em cada ano, via conector MCP independente, em 22 de setembro de 2026.`
- Tarifas-teto (slide 11):
  `Fonte: painel Administração Portuária da ANTAQ, quadros de tarifas-teto e de tarifas homologadas, via conector MCP independente, em 22 de setembro de 2026. Teto aprovado não é preço cobrado.`
- Painel de Fiscalização (slide 12):
  `Fonte: painel Fiscalização da ANTAQ, quadro "Base de Dados", via conector MCP independente, em 22 de setembro de 2026.` No slide 12, acrescentar: `A soma é piso: o painel conta R$ 110,3 milhões.`
- Demonstração ao vivo, art. 34 da Res. 62/2021 (slide 14), única que cita dois quadros:
  `Fonte: painel Fiscalização da ANTAQ, quadros "Base de Dados" e "Objeto das Normas", via conector MCP independente, em 22 de setembro de 2026. Só processo julgado; o que tramita fica fora.`
- Recapitulação do encontro anterior (slide 2):
  `Fonte: apresentação "IA no dia a dia da Fiscalização", SFC, 21 de setembro de 2026 (antaq.github.io/apresentacao_ia_sfc).`
- Campo de instrução (slide 3): `Fonte: instrução sugerida no roteiro desta apresentação (GPF e GRAT/SFC), para uso na demonstração.`
- Instruções da conta (slide 4): `Fonte: campo Instruções para o Claude, em Configurações > Conta, na conta pessoal do apresentador, em 22 de setembro de 2026. Exemplo de uso, não é recomendação da Agência.`
- Roteiro (slide 5): `Fonte: tempo estimado no roteiro desta apresentação (GPF e GRAT/SFC).`
- **Sem linha de fonte:** slides 1, 7, 13, 15 e 16, porque não exibem número.

**Endereço do conector (slides 7 e 16):** `https://antaq.dadosabertos.dev/mcp`. Aparece
projetado nos dois slides, em `'Courier New', monospace`, sempre com o `https://`, porque a
plateia copia isso para a configuração da própria ferramenta. No slide 16 ele é um cartão
**sem link**: clicar abre a resposta crua do servidor no projetor, e não uma página.
Endereço trocado em 21/09/2026; se mudar de novo, os dois slides mudam juntos.

> **Autoria do conector, e é regra de escrita deste deck.** O conector é **projeto pessoal do
> apresentador**, feito com recurso próprio e sem fins lucrativos. A ANTAQ não contratou, não
> desenvolveu, não homologou e não mantém. O que é da Agência é o **dado**, que é publicado;
> a ferramenta não é. Por isso, em texto projetado:
> - **nunca** escrever "conector da ANTAQ", "feito aqui dentro", "feito na Superintendência",
>   "sem custo de contratação" nem atribuição a GPF, GRAT ou SFC;
> - nas linhas de fonte, a forma canônica é **`via conector MCP independente`**;
> - o domínio `dadosabertos.dev` **não** é domínio da Agência, e isso é dito junto com o
>   endereço, nos slides 7 e 16. No slide 14 ele reaparece sem o `https://`, como passo da
>   demonstração, e não como cartão para copiar.
>
> Corrigido em 21/09/2026: até então o slide 7 dizia "feito dentro da própria Superintendência"
> e cinco linhas de fonte atribuíam o conector à GPF.

> Regra que não muda: **todo número projetado tem linha de fonte**. Neste deck, que é todo
> sobre número, a linha de fonte também registra que os valores são nominais, sem correção.

---

## 6. COMPONENTES

### 6.1 Cartão de lista (item numerado ou com ícone)

```html
<div style="background:#F8FAFC;border-left:8px solid #0066CC;border-radius:14px;
            padding:26px 32px;box-shadow:0 2px 8px rgba(0,0,0,.06);">
  <p class="font-montserrat font-bold text-brand-primary" style="font-size:32px;line-height:1.25;">
    <i class="fas fa-ICONE text-brand-secondary" style="margin-right:14px;"></i>Título do item</p>
  <p class="text-gray-600" style="font-size:26px;line-height:1.45;margin-top:8px;">Descrição.</p>
</div>
```
Gradação por ordem nas bordas: `#94A3B8, #60A5FA, #3B82F6, #2563EB, #1D4ED8, #003366`.

### 6.2 Caixa de destaque azul-clara

```html
<div style="background:#F0F9FF;border:3px solid #BAE6FD;border-radius:18px;
            box-shadow:0 10px 25px -5px rgba(0,102,204,.15);padding:34px 44px;">…</div>
```

### 6.3 Duas colunas comparativas (L4)

Duas caixas de largura igual, `gap:40px`, altura igual (`align-items:stretch`).
Rótulo da coluna em pílula no topo. À esquerda o estado "antes/errado"
(neutro cinza: fundo `#F8FAFC`, borda `#E2E8F0`, pílula `#E2E8F0`/`#475569`);
à direita o estado "depois/certo" (fundo `#F0F9FF`, borda `#0066CC`, pílula
`#003366`/branco). Texto do corpo em 30px.
Um conector central opcional: seta `fa-arrow-right-long` em `#0066CC`, 44px.

### 6.4 Tabela (L5)

Wrapper `border-radius:16px; overflow:hidden; border:1px solid #E5E7EB;
box-shadow:0 12px 28px -10px rgba(0,0,0,.18)`.
`thead th`: fundo `#003366`, texto branco, Montserrat 700, 23px, caixa alta,
`padding:20px 26px`, alinhado à esquerda.
`tbody td`: 26px, `#374151`, `padding:20px 26px`, `border-bottom:1px solid #E5E7EB`.
Linhas pares: `background:#F8FAFC`. Primeira coluna em Montserrat 700 `#003366`.
Valor que precisa saltar aos olhos: `font-weight:800; color:#B91C1C`.

### 6.5 Bloco monoespaçado (L6)

```html
<div style="background:#0F172A;border-radius:16px;padding:30px 38px;
            box-shadow:0 14px 30px -12px rgba(0,0,0,.45);">
  <pre style="margin:0;font-family:'Courier New',monospace;font-size:22px;line-height:1.5;
              color:#E2E8F0;white-space:pre-wrap;">…</pre>
</div>
```
Realce de trecho dentro do bloco: `<span style="color:#FCD34D;font-weight:700;">`.
Barra de título do bloco (opcional): faixa `#1E293B` com três círculos e o nome do arquivo.

### 6.6 Faixa vermelha de armadilha: aposentada neste deck

Até 22/09/2026 os slides 8 a 12 traziam a armadilha numa faixa vermelha
(`#FEF2F2` / borda `#DC2626`), rotulada "A ARMADILHA" ou "ANTES DE CONCLUIR". **Elas
foram removidas**: a armadilha passou a ser dita em voz alta, e está escrita na nota do
apresentador de cada slide. O motivo é de leitura: cinco faixas vermelhas seguidas
treinavam a plateia a pular o vermelho, e o alerta perdia o efeito justo onde ele importa.

Quando a leitura precisa ficar em tela, use a **faixa escura** (fundo `#003366`, ícone
`#FFD700`), como nos slides 12 e 14: ela sustenta duas linhas, a manchete em Montserrat
800 e a explicação em `#BAE6FD`.

O **leiaute L7 (captura de tela)** também segue sem uso: o deck foi entregue sem capturas,
com o conteúdo em largura cheia.

### 6.7 Chip de marcador pendente

```css
.marcador { display:inline-flex; align-items:center; gap:12px; background:#FEF3C7;
  border:3px dashed #D97706; color:#92400E; font-family:'Montserrat',sans-serif;
  font-weight:800; border-radius:12px; padding:10px 20px; font-size:24px;
  letter-spacing:.02em; }
```
Componente mantido para quando um dado faltar de novo. **Nenhum slide do deck usa
marcador hoje:** todos foram preenchidos ou removidos em 5 de agosto de 2026.
Em fundo escuro: `background:rgba(253,224,71,.14); color:#FDE68A; border-color:#FDE68A;`.
Marcador dentro de linha de rodapé pode usar 19px.

### 6.8 Faixa-âncora (slides 7 e 15)

```html
<div style="margin-top:34px;background:linear-gradient(90deg,#002244 0%,#004488 100%);
            border-left:12px solid #FFD700;border-radius:0 14px 14px 0;padding:26px 40px;
            display:flex;align-items:center;gap:24px;">
  <i class="fas fa-signature" style="color:#FFD700;font-size:40px;"></i>
  <p class="font-montserrat" style="color:#FFFFFF;font-size:36px;font-weight:800;line-height:1.2;">
    A IA não assina. Quem assina é você, e quem assina responde.</p>
</div>
```

### 6.9 Destaque numérico (L8)

Número em Montserrat 900, 120 a 190px, `#003366` (ou `#FFD700` em fundo escuro),
com rótulo em caixa alta 26px acima e explicação 26px abaixo.

### 6.10 Pílula de passo

```html
<span style="font-family:'Montserrat',sans-serif;font-weight:800;font-size:20px;color:#1E3A8A;
  padding:8px 20px;border-radius:999px;background:#DBEAFE;text-transform:uppercase;
  letter-spacing:.06em;">Passo 1</span>
```

### 6.11 Item de proibição (slide 16)

```html
<div style="background:#FEF2F2;border:3px solid #FCA5A5;border-left:10px solid #DC2626;
            border-radius:14px;padding:22px 30px;display:flex;align-items:center;gap:22px;">
  <i class="fas fa-ban" style="color:#DC2626;font-size:38px;flex-shrink:0;"></i>
  <p style="font-size:30px;color:#7F1D1D;font-weight:600;line-height:1.3;">Texto do veto.</p>
</div>
```
Slides 4, 7, 13, 14 e 16 serão fotografados pela plateia: **contraste alto, texto grande,
sem elementos decorativos que roubem espaço**.

### 6.12 Campo de instrução (slides 3 e 4)

Caixa de vidro sobre fundo escuro, para o texto que a plateia vai copiar. Vem do deck de
IA de 21/09/2026 e é o único componente claro em cima do gradiente.

```html
<div class="campo">
  <div class="campo-topo">
    <i class="fas fa-ICONE" style="color:#FFD700; font-size:32px;"></i>
    <span class="campo-rotulo">Rótulo do campo</span>
  </div>
  <p class="instrucao">Texto da instrução.<span class="cursor"></span></p>
</div>
```
```css
.campo { background:rgba(255,255,255,0.07); border:2px solid rgba(255,255,255,0.24);
  border-radius:22px; padding:32px 44px 40px 44px; max-width:1700px;
  box-shadow:0 22px 48px -18px rgba(0,0,0,0.55); }
.campo-topo { display:flex; align-items:center; gap:16px; padding-bottom:20px;
  border-bottom:1px solid rgba(255,255,255,0.16); margin-bottom:28px; }
.campo-rotulo { font-family:'Montserrat',sans-serif; font-weight:800; font-size:20px;
  text-transform:uppercase; letter-spacing:.2em; color:#BFDBFE; }
.instrucao { font-family:'Montserrat',sans-serif; font-weight:600; font-size:46px;
  line-height:1.34; color:#FFFFFF; letter-spacing:-0.01em; }
.cursor { display:inline-block; width:15px; height:42px; background:#FFD700;
  margin-left:12px; vertical-align:-7px; animation:pisca 1.1s step-end infinite; }
@keyframes pisca { 0%,100% { opacity:1; } 50% { opacity:0; } }
```

Regras:

- **Sem aspas ao redor da instrução.** A plateia copia e cola, e as aspas atrapalham.
  O trecho que cada pessoa troca vai em `#FFD700`, dentro de `<b>`.
- Uma frase só: `.instrucao` a 46px (slide 3). Três parágrafos: 33px, com
  `.instrucao + .instrucao { margin-top:26px; }` e cursor só no último (slide 4).
- Fecho em Montserrat 800, 40px, `#FFD700`, precedido de barra dourada de 90x8px.
- Rótulo acima da caixa (a "sobrancelha"): barra dourada 72x4 e texto 22px `#BFDBFE`,
  caixa alta, `letter-spacing:.3em`.

---

## 7. SLIDES ESCUROS (capa, divisórias, frases de impacto L2, encerramento)

Fundo com o gradiente da seção 2, `color:white`. Sempre:

```html
<div class="absolute left-0 top-0 h-full w-3 z-20" style="background:#FFD700;"></div>
<div class="absolute left-3 top-0 h-full w-1 z-20" style="background:#0066CC;"></div>
```
Marca d'água: `Imagens/logo-antaq-branca.png` a `opacity:.06`, ou `logo-antaq-azul.png`
com `filter:brightness(0) invert(1)` a `opacity:.07-.08`.
Ícone decorativo gigante FontAwesome no canto inferior direito, `font-size:480-520px;
opacity:.05`. Padrão de pontos opcional:
`background-image: radial-gradient(rgba(255,255,255,.05) 1px, transparent 1px); background-size:22px 22px;`

### 7.1 Divisória de bloco (L10), slide 5

Espelham `../GPFTrilhaTecnico/apresentacao/slide-04.html`:
rótulo "BLOCO" com barra dourada; número em dourado 188px; título 84px;
linha-resumo 30px; e, no lugar dos "chips", **uma pílula de tempo estimado**:

```html
<span style="display:inline-flex;align-items:center;gap:16px;border:2px solid rgba(255,215,0,.55);
  background:linear-gradient(90deg,rgba(255,215,0,.16),rgba(255,215,0,.04));border-radius:999px;
  padding:18px 36px;">
  <i class="fas fa-clock" style="color:#FFD700;font-size:30px;"></i>
  <span class="font-montserrat" style="font-size:30px;font-weight:800;color:#fff;">10 minutos</span>
</span>
```
Mais 3 a 4 "chips" com os pontos do bloco (padrão do slide-04 de referência, 22px).

### 7.2 Frase de impacto em tela cheia (L2), slide 13

Fundo escuro, sem header. Texto centralizado verticalmente, alinhado à esquerda a partir
de `padding-left:130px`, largura máxima 1560px. Aspas decorativas `fa-quote-left` em
dourado, `opacity:.5`, 90px. Texto 56 a 84px, Montserrat 800, `line-height:1.22`.
Palavra-chave em `#FFD700`. Rodapé escuro (5.3). **Não altere o texto destes slides.**

---

## 8. NOTAS DO APRESENTADOR (em TODO slide, antes do script de navegação)

Bloco oculto, nunca projetado, enviado ao `index.html`, que o exibe em painel lateral
com a tecla **N**.

```html
<div id="notas-apresentador" style="display:none;">
  <p>Primeiro parágrafo da nota.</p>
  <p>Segundo parágrafo.</p>
</div>
<script>window.addEventListener("load",function(){var n=document.getElementById("notas-apresentador");window.parent.postMessage({type:"slide-notes",html:n?n.innerHTML:""},"*");});</script>
```

Se a especificação não trouxer NOTAS para o slide, escreva uma nota curta e útil
(o que dizer, quanto tempo segurar, para onde olhar). Nunca deixe o bloco vazio.

---

## 9. SCRIPT DE NAVEGAÇÃO (último elemento do body, VERBATIM, em TODOS os slides)

```html
<script>document.addEventListener("keydown",function(e){if(["ArrowRight","ArrowLeft","PageDown","PageUp","Home","End"," ","f","F","n","N"].indexOf(e.key)!==-1){e.preventDefault();window.parent.postMessage({type:"slide-nav",key:e.key},"*");}});</script>
```

---

## 10. MAPA DOS SLIDES

| # | Leiaute | Assunto | Tag | Vinha de |
|---|---|---|---|---|
| 1 | L1 | Capa | sem tag | novo |
| 2 | L3 | O que ficou dito ontem (recapitulação) | ABERTURA | novo |
| 3 | L2+6.12 | Campo de instrução: como começar sem saber por onde | sem tag | slide 28 do deck de IA |
| 4 | L2+6.12 | Instruções para o Claude, em Configurações > Conta | sem tag | novo |
| 5 | L10 | Divisória bloco 1, Cinco perguntas e uma ao vivo (24 min) | sem tag | 28 |
| 6 | L6+L4 | A mesma pergunta, com e sem conector | DADOS ABERTOS | 29 |
| 7 | L3 | O conector não é um sistema da ANTAQ, endereço e faixa-âncora | DADOS ABERTOS | 30 |
| 8 | L6+6.1 | Caso 1: onze contratos vencem até dezembro | DADOS ABERTOS | 31 |
| 9 | L6+L8 | Caso 2: a empresa inteira em uma pergunta | DADOS ABERTOS | 33 |
| 10 | L6+L8 | Caso 3: sobre-estadia, de 14 para 72 acórdãos por ano | DADOS ABERTOS | novo |
| 11 | L6+L8 | Caso 4: onze tetos na forma genérica, um na específica | DADOS ABERTOS | novo |
| 12 | L6+6.1 | Caso 5: a maior carteira não é a de maior valor | DADOS ABERTOS | novo |
| 13 | L2 | Conclusão do bloco: transparência no papel, ou funcionando | sem tag | 36 |
| 14 | L6+L4 | Demonstração ao vivo: o panorama do art. 34 da Res. 62/2021, em PDF | DADOS ABERTOS | novo |
| 15 | L6+6.8 | Traga a pergunta da sua unidade, com faixa-âncora | DADOS ABERTOS | 37 |
| 16 | L11 | Contato, material, endereço do conector e código de leitura óptica | sem tag | 41 |

A coluna "Vinha de" traz a numeração no deck de 21/09/2026. Ela existe para que quem
comparar os dois materiais encontre o slide equivalente sem procurar.

## 11. CARTÃO DE COMPARTILHAMENTO (OPEN GRAPH)

Quando o endereço da apresentação é colado no WhatsApp, no Teams ou numa rede social, o
aplicativo lê as metaetiquetas do `index.html` e mostra um cartão. Sem elas, aparece só o
endereço cru.

**Arquivos**

| Arquivo | Papel |
|---|---|
| `Imagens/og-capa.jpg` | a imagem publicada, 1200x630, JPEG, 121 KB |
| `Imagens/og-fonte.html` | a página que gera a imagem. Não é publicada como tela |

**Regras da imagem**

- **1200x630 exatos** e **abaixo de 300 KB**. O WhatsApp descarta a prévia de arquivos grandes.
- JPEG, não PNG: o mesmo cartão em PNG passa de 300 KB.
- A arte segue o fundo escuro da capa (gradiente `#002244` a `#004488`), com barra dourada
  à esquerda, logotipo, rótulo, título, régua dourada, subtítulo, data e autoria.
- `og-fonte.html` tem `* { box-sizing: border-box; }`. Sem isso o `padding` do cartão soma
  à largura, o conteúdo passa de 1200px e a marca d'água sai do enquadramento.

**Como regerar a imagem**

```bash
python3 -m http.server 8181          # na pasta acima do deck
```
Abrir `http://localhost:8181/Dados-Abertos-Analise-Tecnica/Imagens/og-fonte.html?deck=dados` numa janela de
**1200x630**, capturar em JPEG com qualidade 88 e salvar como `Imagens/og-capa.jpg`.
O mesmo arquivo atende aos dois decks: o parâmetro `?deck=` escolhe ícone, título, subtítulo
e data.

**Metaetiquetas no `index.html`**

Ficam logo depois dos ícones, antes das fontes. São 19, e três detalhes não podem faltar:

- `og:image` com **endereço absoluto em https**. Caminho relativo não funciona.
- `og:image:width` 1200 e `og:image:height` 630, para o aplicativo reservar o espaço certo.
- `twitter:card` igual a `summary_large_image`, senão o cartão vem pequeno e cortado.

Depois de publicar, o WhatsApp guarda a prévia em cache por dias. Para conferir uma troca,
use o depurador do Facebook, que força a releitura, ou acrescente `?v=2` ao endereço.
