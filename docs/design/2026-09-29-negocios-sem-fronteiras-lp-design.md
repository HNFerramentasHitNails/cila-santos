# Negócios Sem Fronteiras — Especificação de design da Landing Page

- **Data:** 29 de setembro de 2026
- **Fonte do conteúdo:** `Estudo_LP_Formacao_Brasil_Cila_Bruno.pdf` (9 páginas, manual de conteúdo)
- **Destino:** novo projecto Lovable, workspace **HN Principal**
- **Estado:** especificação v2 (29/09/2026): LP informativa, sem inscrição; correcções depois da revisão da 1ª versão no Lovable.

---

## 0. O essencial em 5 linhas

- **O que é:** página **informativa** sobre uma formação presencial de 1 dia (20/10/2026, a partir das 10h00, BE Factory, São Paulo). **Não tem inscrição:** sem botões de inscrição, sem formulário e sem barra fixa (decisão do Diogo em 29/09/2026).
- **Para quem:** empresários brasileiros que já têm um negócio a funcionar e querem multiplicá-lo.
- **O único trabalho da página:** apresentar a formação, os três sócios e o ecossistema com autoridade, até a pessoa fixar a data e o local.
- **Narrativa (do PDF):** Portugal → Brasil → parceria empresarial → ecossistema real → experiência prática → novas oportunidades → o encontro (data e local).
- **Língua da página:** português do Brasil. O público é brasileiro, e o título do PDF já está em PT-BR. A única frase que fica em PT-PT é a citação da Cila, porque é a voz dela.

---

## 1. Conceito visual: "Mar Largo"

O Atlântico entre Lisboa e São Paulo, desenhado com a pedra que os dois países partilham.

| Decisão | Porquê (a história para contar à Cila e ao Bruno) | Fonte |
|---|---|---|
| **Onda da calçada portuguesa ("Mar Largo")** como assinatura gráfica | O padrão de ondas pretas e brancas foi criado no Rossio, em Lisboa (concluído em 1849, Eusébio Furtado). O calçadão de Copacabana adoptou o mesmo desenho como homenagem à herança portuguesa. É, literalmente, o mar que separa os dois países desenhado com a pedra que os une. | pt.wikipedia.org/wiki/Mar_largo; pt.wikipedia.org/wiki/Calçadão_de_Copacabana |
| **Preto basalto + branco calcário** como base | São as duas pedras da calçada. Coincidem com a foto (Bruno de preto, Cila de branco) e com o preto e branco das marcas HN e Elite Mind Business. | foto enviada; hnhitnails.com; elitemindbusiness.com |
| **Vermelho pau-brasil** como único acento | O corante vermelho do pau-brasil foi o primeiro grande negócio entre o Brasil e Portugal (ciclo a partir de 1503) e deu nome ao país. É a cor do "primeiro negócio sem fronteiras". Na foto, também é o vermelho da bandeira portuguesa atrás do Bruno. | nationalgeographicbrasil.com (2022); brasilianaiconografica.art.br |
| **Tipografia que se alarga** (eixo de largura da Archivo) | "Multiplicar" e "expandir" ditos pela própria letra: no carregamento, o título passa de estreito a largo. | fonts.google.com/specimen/Archivo (eixo wdth 62–125 verificado na API) |

### Auto-revisão contra o "design genérico" (skill frontend-design)

| Primeira ideia | Porque a troquei | Ficou |
|---|---|---|
| Preto + dourado (o dourado do PDF) | É o visual "evento premium" por defeito e não diz nada sobre Portugal e Brasil | Basalto + calcário + pau-brasil, com origem na calçada e no pau-brasil |
| Arco de voo sobre um mapa escuro Lisboa → São Paulo | Truque comum de "internacional" | Onda Mar Largo, que só este tema tem |
| Fade-up em todas as secções | Denuncia página gerada | 3 momentos de movimento com significado (secção 6) |
| Marcadores 01/02/03 nas secções | O conteúdo não é uma sequência | Sem numeração. Estrutura dada por cor e pela onda |
| Etiquetas em maiúsculas por cima de cada título | Ruído e sinal de template | Títulos em sentence case. Só existem etiquetas quando informam (ex.: "Data") |

---

## 2. Cor

| Token | Hex | Papel | Contraste verificado (WCAG) |
|---|---|---|---|
| `--calcario` | `#F2EFE9` | Fundo dominante (≈60%) | basalto sobre calcário **15,15:1** |
| `--basalto` | `#1B1A18` | Texto principal, secções escuras, ondas (≈30%) | calcário sobre basalto **15,15:1** |
| `--pedra` | `#67635B` | Texto secundário sobre calcário | **5,21:1** |
| `--cinza` | `#A5A095` | Texto secundário sobre basalto | **6,68:1** |
| `--linha` | `#D8D3C9` | Filetes e divisores sobre calcário (só decorativo) | — |
| `--pau-brasil` | `#A8262B` | Acento sobre fundo claro | branco sobre ele **7,05:1**; ele sobre calcário **6,15:1** |
| `--brasa` | `#C73A33` | O mesmo acento sobre fundo escuro | branco sobre ele **5,15:1**; ele sobre basalto **3,38:1** |

**Onde o acento pode aparecer (e mais nenhum sítio):**
1. A data "20 de outubro de 2026" no hero, nas informações práticas e no encerramento.
2. Linha de progresso de leitura no header.
3. Estado activo do diagrama do ecossistema (hover, foco ou toque).
4. As aspas da citação da Cila.

Sem gradientes decorativos e sem sombras. A profundidade vem dos blocos de cor e da fotografia.

---

## 3. Tipografia

**Uma só família: Archivo** (Google Fonts, variável: peso 100–900, largura 62–125%).
`https://fonts.googleapis.com/css2?family=Archivo:ital,wdth,wght@0,62..125,100..900;1,62..125,100..900&display=swap`
Fallback: `"Archivo", "Helvetica Neue", Arial, sans-serif`.

A personalidade vem da **largura**: títulos largos (112–125%), texto normal (100%) e números condensados (62–75%).

| Papel | Desktop | Mobile | Peso | Largura | Entrelinha | Tracking |
|---|---|---|---|---|---|---|
| Display (hero) | 84px | 42px | 900 | 112% | 0.95 | -0.03em |
| Manifesto | clamp(40px, 6.5vw, 104px) | 40px | 850 | 125% | 0.98 | -0.03em |
| H2 (secção) | clamp(34px, 4.4vw, 64px) | 34px | 800 | 118% | 1.02 | -0.025em |
| H3 | 26px | 22px | 700 | 108% | 1.2 | -0.01em |
| Lead | 22px | 19px | 400 | 100% | 1.55 | 0 |
| Corpo | 18px | 17px | 400 | 100% | 1.65 | 0 |
| Pequeno / meta | 15px | 15px | 500 | 100% | 1.45 | 0 |
| Etiqueta de dado | 14px | 14px | 600 | 100% | 1.4 | 0.01em (sentence case) |
| Botão | 17px | 17px | 700 | 110% | 1 | 0 |
| Números (contador, data) | 96px | 56px | 700 | 68% | 1 | -0.02em, `tabular-nums` |

Regras:
- `text-wrap: balance` em todos os títulos.
- Corpo com no máximo 62 caracteres por linha (`max-width: 62ch`).
- Nada de maiúsculas em etiquetas. Títulos em sentence case.
- Citação da Cila: Archivo itálico, 400, largura 100%, 32–44px, com aspas em pau-brasil.

---

## 4. Grelha, espaçamento, forma

- **Grelha:** 12 colunas, conteúdo com máximo de 1320px, gutter de 24px. Margens laterais de 20px (mobile), 40px (tablet) e 64px (desktop).
- **Alinhamento:** tudo alinhado à esquerda, com composição editorial assimétrica (título numa coluna larga, texto noutra). Nada centrado, excepto o bloco do convite do Paulo.
- **Espaçamento (base 4):** 4, 8, 12, 16, 24, 32, 48, 64, 96, 128, 160.
- **Padding vertical de secção:** 160px (desktop), 112px (tablet), 80px (mobile).
- **Raios por hierarquia:** fotos 0; tiles do ecossistema 0 com filete; cartão do encerramento 4px.
- **Ícones:** lucide-react, traço 1.5, 20px. Usados só em informações práticas (calendário, relógio, pin, pessoas) e em links externos (`arrow-up-right`, que indica "abre noutro separador").

---

## 5. Imagem

- **Foto principal:** Cila (de branco) e Bruno (de preto) de costas um para o outro, com as bandeiras de Portugal e do Brasil atrás. Retrato 2:3 (1024×1536).
  - **No hero:** a cores, na metade direita, a sangrar até à margem direita e ao topo. Máscara em gradiente para o basalto na esquerda (0→35%) e em baixo. `object-position: center 15%`, para as caras ficarem sempre visíveis.
  - **Nas bios:** recortes da mesma foto a preto e branco (`grayscale(1) contrast(1.08)`), 4:5. Bruno com `object-position: 28% 18%`, Cila com `object-position: 74% 18%`.
  - **Ficheiro:** `src/assets/cila-bruno.jpg` (carregado pelo Diogo no Lovable em 29/09/2026).
- **Paulo Kazaks:** foto real em `src/assets/paulo-kazaks.png` (carregada pelo Diogo em 29/09/2026), 4:5. Substitui o monograma "PK".
- **Bio da Cila:** foto individual `src/assets/cila-santos.jpg`, carregada pelo Diogo em 29/09/2026.
- **Bio do Bruno:** foto individual carregada pelo Diogo em 29/09/2026 (prevista em `src/assets/bruno-rosado.*`). O recorte da foto do hero, descrito abaixo, só se usa se a individual faltar.
- **Regra de série:** os três retratos (Cila, Bruno, Paulo) usam o mesmo formato (4:5) e o mesmo tratamento de cor.
- **Recorte do Bruno:** janela da foto do hero de x 5%–51% e y 9%–47% (imagem com width 217%, left -11%, top -23% num contentor 4:5). Só o Bruno, sem nenhum pedaço da Cila. A 1ª versão mostrava a foto dupla inteira.
- **Preto e branco que passa a cores (pedido do Diogo, 29/09/2026):** os retratos estão em `grayscale(1) contrast(1.05)`.
  - Com rato: ao passar sobre o bloco da pessoa (ou com foco dentro dele) passam a cores, com `filter` em 500ms `cubic-bezier(.16,1,.3,1)`.
  - Em ecrã tátil: passam a cores quando ficam 60% visíveis e ficam assim.
  - Com `prefers-reduced-motion`: a mudança é instantânea.
- **Onda Mar Largo:** componente SVG próprio (Apêndice A), com textura de pedras irregulares, as juntas da calçada. Nunca imagem rasterizada.

---

## 6. Movimento

Três momentos com significado. Tudo o resto é resposta a acções da pessoa. Com `prefers-reduced-motion: reduce`, tudo aparece no estado final, sem animação.

1. **Carregamento do hero (uma vez, cerca de 1,6s)**
   - 0ms: a foto passa de opacidade 0 e escala 1.04 para 1, em 1200ms, `cubic-bezier(.16,1,.3,1)`.
   - 150ms: "Paulo Kazaks convida Cila Santos & Bruno Rosado" entra com fade de 400ms.
   - 250ms: cada linha do título anima `font-stretch` de 75% para 112%, opacidade de 0 para 1 e y de 12px para 0, em 900ms, com 110ms entre linhas. **Só no desktop**, onde cada linha tem `white-space: nowrap`. No mobile, só opacidade e y.
   - 800ms: subtítulo e linha de informações entram com fade de 400ms.
2. **A onda atravessa (ligada ao scroll):** no fundo do hero, a faixa Mar Largo desliza na horizontal um comprimento de onda (384 unidades) enquanto o hero sai do ecrã. Quem faz scroll está a "atravessar o Atlântico". Não há animação em loop.
3. **Ecossistema a ligar-se:** quando o diagrama fica 35% visível, as ligações desenham-se a partir da HN Hit Nails (`pathLength` de 0 para 1, 1000ms, 80ms entre ligações), uma só vez.
   - **Manifestos:** nas 3 frases-manifesto, cada palavra passa de opacidade .22 para 1 enquanto a frase atravessa o ecrã (dos 80% aos 35% da altura), ligado ao scroll.

**Micro-interacções:**
- **Retratos:** passam de preto e branco a cores no hover/foco (500ms). Em ecrã tátil, passam quando ficam visíveis (ver secção 5).
- **Tiles do ecossistema:** invertem para fundo basalto no hover e no foco (200ms).
- **FAQ:** acordeão abre em 250ms.
- **Linha de progresso do header:** `scaleX` ligado ao scroll da página.
- **Contador:** números mudam sem efeito.

Proibido: fade-up por secção, parallax em fotos, cursores personalizados, contadores a "rolar".

---

## 7. Estrutura, posições e texto (PT-BR)

A ordem segue o ponto 10 do PDF (14 blocos). A Cila e o Bruno ficam num só spread, tal como a parceria e o Paulo.

### Header (fixo, 64px, basalto)
`[Negócios Sem Fronteiras]` (Archivo 800, largura 125%, 16px, calcário) à esquerda.
"20 de outubro | São Paulo" (15px, 500, cinza) à direita. Não há botão.
Sem menu. Em baixo, linha de progresso de 2px em pau-brasil.

### 01 Hero (basalto)
```
DESKTOP 1440
┌──────────────────────────────────────────────────────────────────────┐
│ Negócios Sem Fronteiras                   20 de outubro | São Paulo  │
├───────────────────────────────────┬──────────────────────────────────┤
│ Paulo Kazaks convida              │                                  │
│ Cila Santos & Bruno Rosado        │     FOTO Cila & Bruno (2:3)      │
│                                   │     sangra à direita e ao topo   │
│ Seu negócio já funciona.          │     gradiente → basalto à esq.   │
│ Agora ele precisa                 │                                  │
│ se multiplicar.                   │                                  │
│                                   │                                  │
│ Formação presencial para empre-   │                                  │
│ sários que já construíram algo    │                                  │
│ e querem multiplicar essa         │                                  │
│ estrutura.                        │                                  │
│                                   │                                  │
│ 20 de outubro de 2026 │ A partir das 10h00 │ BE Factory, São Paulo  │
├───────────────────────────────────┴──────────────────────────────────┤
│≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈ faixa Mar Largo, 180px, desliza com scroll ≈≈≈≈≈≈≈≈≈│
│ Lisboa 38°43′N 9°08′W                     São Paulo 23°33′S 46°38′W │
└──────────────────────────────────────────────────────────────────────┘
Texto: colunas 1–6. Foto: colunas 7–12 + margem. Altura do hero: máx. 880px.

MOBILE 375
┌─────────────────────┐
│ NSF   20 out | SP   │
│ FOTO 4:5 (caras)    │
│ gradiente em baixo  │
│ Paulo Kazaks convida│
│ Cila & Bruno        │
│ Seu negócio já      │
│ funciona. Agora ele │
│ precisa se          │
│ multiplicar.        │
│ subtítulo           │
│ 20 out 2026 | 10h00 │
│ BE Factory, SP      │
│≈≈≈≈ Mar Largo ≈≈≈≈≈│
└─────────────────────┘
```
- **Linha de convite:** "Paulo Kazaks convida Cila Santos & Bruno Rosado". Em cinza, 16px, 600, com os nomes em calcário.
- **Título:** "Seu negócio já funciona. Agora ele precisa se multiplicar."
- **Subtítulo:** "Uma formação presencial para empresários que já construíram algo e querem transformar essa estrutura em novos produtos, novos canais e novas fontes de receita."
- **Linha de informações:** 3 blocos separados por filete vertical: "20 de outubro de 2026" (brasa), "A partir das 10h00", "BE Factory, São Paulo". Não usar pontos médios.
- **Coordenadas:** 13px, cinza, `tabular-nums`, numa linha de 40px em basalto logo **acima** da onda ("Lisboa…" à esquerda, "São Paulo…" à direita). Nunca por cima das ondas, onde ficam ilegíveis (erro visto na 1ª versão).
- **O título nunca entra na coluna da foto:** no desktop, 4 linhas explícitas com `nowrap`: "Seu negócio" / "já funciona." / "Agora ele precisa" / "se multiplicar.". Usa o maior tamanho (máximo 84px) em que "Agora ele precisa" cabe na coluna do texto a 1280, 1440 e 1920px. A 2ª versão ficou em 5 linhas, com "precisa" sozinho. Na 1ª versão, a 1920px, a 1ª linha ia até aos ~75% da largura, por cima da foto.

### 02 De Portugal para o Brasil (calcário)
```
┌──────────────────────────────────────────────────────────────────────┐
│ Eles não vêm falar sobre teoria.   │ No dia 20 de outubro, Cila Santos│
│ Vêm compartilhar o que             │ e Bruno Rosado vêm ... (corpo)   │
│ construíram na prática.  (H2 1–7)  │ (colunas 8–12)                   │
│──────────────────────────────────────────────────────────────────────│
│ Portugal ─────────────────────────────────────────────── Brasil       │
│ Um único dia          Presencial            BE Factory, São Paulo     │
└──────────────────────────────────────────────────────────────────────┘
```
- **H2:** "Eles não vêm falar sobre teoria. Vêm compartilhar o que construíram na prática."
- **Corpo:**
  - "No dia 20 de outubro, Cila Santos e Bruno Rosado vêm diretamente de Portugal para o Brasil, a convite de Paulo Kazaks, para uma formação presencial destinada a empresários que querem entender como transformar um negócio em uma estrutura capaz de gerar novos produtos, novos canais e novas fontes de receita."
  - "O ponto de partida é a experiência dos dois como empresários e a construção do ecossistema que desenvolveram em Portugal."
  - "E esta formação não nasce de uma ligação ocasional: Paulo Kazaks, Cila Santos e Bruno Rosado são sócios na HM Negócios, uma parceria que liga Portugal e Brasil."
- **Linha de rota:** filete de 1px com "Portugal" à esquerda e "Brasil" à direita. Por baixo, 3 factos: "Um único dia", "Presencial", "BE Factory, São Paulo".

### 03 + 04 Cila Santos e Bruno Rosado (calcário)
```
┌──────────────────────────────────────────────────────────────────────┐
│ [foto Cila P&B 4:5]              │                                   │
│ Cila Santos (H2)                 │  [foto Bruno P&B 4:5]  ← desce 96px│
│ Empresária, CEO e uma das forças │  Bruno Rosado (H2)                │
│ por trás do ecossistema HN...    │  Empresário, CEO e responsável... │
│ bio                              │  bio                              │
│ Na formação: marca, posiciona... │  Na formação: estrutura, ...      │
├──────────────────────────────────────────────────────────────────────┤
│ “O objetivo não é criar negócios aleatórios. É perceber tudo aquilo  │
│  que pode nascer à volta de um negócio que já funciona.” — Cila      │
└──────────────────────────────────────────────────────────────────────┘
Cila: colunas 1–6. Bruno: colunas 7–12, com a coluna desalinhada 96px para baixo.
Mobile: empilhado, primeiro a Cila.
```
- **Cila Santos**
  - Papel: "Empresária, CEO e uma das forças por trás do ecossistema HN Hit Nails."
  - Bio: "Cila Santos construiu sua trajetória empresarial a partir do setor da beleza, mas sua visão logo ultrapassou a criação de uma única marca ou de uma única fonte de faturamento. Ao longo dos anos, transformou conhecimento, experiência, marca e comunidade em diferentes oportunidades de negócio, desenvolvendo áreas que se complementam e fortalecem o mesmo ecossistema. Hoje, seu trabalho cruza beleza, educação, formação empresarial, desenvolvimento de marcas, comunidade e novos projetos de negócio."
  - Na formação: "Marca, posicionamento, vendas, criação de comunidade e identificação de novas oportunidades a partir do que o empresário já construiu."
- **Bruno Rosado**
  - Papel: "Empresário, CEO e responsável por uma visão de gestão, estrutura e tecnologia aplicada ao crescimento empresarial."
  - Bio: "Se Cila representa a visão de marca, comunicação e expansão comercial, Bruno acrescenta ao ecossistema uma vertente essencial: estrutura, gestão, processos, números e tecnologia. Sua atuação está ligada à construção das estruturas que permitem transformar ideias e oportunidades em negócios organizados, escaláveis e integrados. É também nessa visão que entram os projetos tecnológicos e as soluções de gestão desenvolvidos dentro do próprio ecossistema."
  - Na formação: "Por que multiplicar um negócio não significa simplesmente lançar mais produtos, e por que crescer de forma sustentável exige estrutura, processos, gestão e sistemas capazes de suportar esse crescimento."
- **Citação (PT-PT original):** "O objetivo não é criar negócios aleatórios. É perceber tudo aquilo que pode nascer à volta de um negócio que já funciona." — Cila Santos

### 05 O ecossistema que construíram (basalto)
```
┌──────────────────────────────────────────────────────────────────────┐
│ Um negócio pode ser o início.       │ corpo (colunas 8–12)           │
│ Não precisa ser o fim. (H2)         │                                │
│                                                                      │
│                          ╭──── Formação e educação                   │
│                          ├──── Escola de negócios                    │
│  ● HN Hit Nails ─────────┼──── Comunidade                 [painel:   │
│   Produtos, marca e      ├──── Tecnologia e software       descrição │
│   distribuição           ├──── Eventos                     do nó     │
│                          ╰──── Novas marcas e projetos     activo]   │
│                                                                      │
│ Novos produtos. Novos canais. Novas receitas. Um único ecossistema.  │  ← manifesto
│ fecho (colunas 1–7)                                                  │
└──────────────────────────────────────────────────────────────────────┘
Mobile: a origem em cima; os 6 nós em coluna, ligados por uma linha vertical com ramificações; a descrição sempre visível por baixo de cada nó.
```
- **H2:** "Um negócio pode ser o início. Não precisa ser o fim."
- **Corpo:** "A trajetória de Cila Santos e Bruno Rosado mostra exatamente o conceito que estará no centro desta formação: como transformar conhecimento, audiência, estrutura e oportunidades em diferentes negócios que se alimentam entre si. A HN Hit Nails é uma das peças de uma visão empresarial mais ampla. Com o crescimento do grupo, foram surgindo áreas, projetos e soluções que se conectam e criam novas possibilidades de faturamento, posicionamento e expansão."
- **Nós do diagrama** (origem mais 6, SVG com curvas bezier, ligações em `--cinza` a 40% que ficam em brasa quando activas):
  - HN Hit Nails: Produtos, marca e distribuição (origem, maior, sempre em calcário)
  - Formação e educação: Conhecimento transformado em novas soluções
  - Escola de negócios: Desenvolvimento empresarial
  - Comunidade: Relação, audiência e recorrência
  - Tecnologia e software: Gestão e soluções digitais
  - Eventos: Experiência, autoridade e novas oportunidades
  - Novas marcas e projetos: Expansão do ecossistema
- Os nós são `<button>`, focáveis, com `aria-pressed`. O primeiro nó começa activo.
- **Manifesto:** "Novos produtos. Novos canais. Novas receitas. Um único ecossistema."
- **Fecho:** "É exatamente essa experiência que Cila e Bruno vêm compartilhar com empresários brasileiros: não apenas o que funcionou, mas também como foram identificando oportunidades, criando novas áreas e estruturando cada passo para que o crescimento não dependesse de uma única fonte de receita."

### 06 Conheça o ecossistema por dentro (calcário)
```
┌──────────────────────────────────────────────────────────────────────┐
│ Não estamos só falando sobre construir um ecossistema.               │
│ Estamos mostrando um que já existe. (H2, colunas 1–9)                │
│ ┌───────────────┬───────────────┬───────────────┬───────────────┐    │
│ │ HN Hit Nails  │ Cila Santos   │ Elite Mind    │ Fluxus        │    │
│ │ descrição     │ descrição     │ Business      │ descrição     │    │
│ │               │               │ descrição     │               │    │
│ │ Conhecer a HN ↗│ Conhecer Cila ↗│ Conhecer a  ↗ │ Conhecer a   ↗│    │
│ └───────────────┴───────────────┴───────────────┴───────────────┘    │
│ Produto. Marca. Educação. Tecnologia.  (manifesto)                   │
│ Negócios diferentes. Uma visão comum.                                │
└──────────────────────────────────────────────────────────────────────┘
Tablet: 2×2. Mobile: empilhado. Tiles com filete de 1px basalto, sem sombra; no hover e no foco invertem para basalto.
```
| Tile | Descrição | CTA | URL (abre noutro separador) |
|---|---|---|---|
| HN Hit Nails | A marca que está na origem do ecossistema. | Conhecer a HN Hit Nails | https://www.hnhitnails.com |
| Cila Santos | Marca pessoal, posicionamento e desenvolvimento empresarial. | Conhecer Cila Santos | https://www.cilasantos.com |
| Elite Mind Business | Conhecimento transformado em educação empresarial. | Conhecer a Elite Mind Business | https://www.elitemindbusiness.com |
| Fluxus | Tecnologia criada para responder às necessidades reais da gestão. | Conhecer a Fluxus | https://fluxus.elitemindbusiness.com |

Os links têm `target="_blank" rel="noopener noreferrer"` e `aria-label` com "(abre em nova aba)". Repetem-se de forma discreta no footer, como pede o PDF.

### 07 + 08 Portugal + Brasil: HM Negócios e Paulo Kazaks (calcário, com o convite em basalto)
```
┌──────────────────────────────────────────────────────────────────────┐
│ Uma parceria que já liga            │ corpo (colunas 8–12)           │
│ Portugal ao Brasil. (H2)            │                                │
│ ┌─────────────────────┬──────┬─────────────────────┐                 │
│ │ Portugal            │≈≈≈≈≈≈│ Brasil              │                 │
│ │ Cila Santos         │≈HM ≈≈│ Paulo Kazaks        │                 │
│ │ Bruno Rosado        │Negó- │                     │                 │
│ │                     │cios≈≈│                     │                 │
│ └─────────────────────┴──────┴─────────────────────┘                 │
│   faixa Mar Largo VERTICAL (120px) = o Atlântico entre os sócios     │
│ Sócios. Empresários. Dois países. Uma visão de crescimento. (manif.) │
│                                                                      │
│ [PK monograma 4:5]  │ Quem é Paulo Kazaks? (H2) + bio                │
├──────────────────────────────────────────────────────────────────────┤
│ (basalto, centrado)  Paulo Kazaks convida                            │
│                      Cila Santos & Bruno Rosado                      │
│                      Diretamente de Portugal para o Brasil.          │
└──────────────────────────────────────────────────────────────────────┘
Mobile: Portugal / faixa horizontal com "HM Negócios" / Brasil.
```
- **H2:** "Uma parceria que já liga Portugal ao Brasil."
- **Corpo:** "A relação entre Portugal e Brasil existe antes desta formação. Paulo Kazaks, Cila Santos e Bruno Rosado são sócios na HM Negócios, uma parceria empresarial que une os dois países. Não são apenas empresários portugueses que viajam ao Brasil para dar uma formação. São sócios e parceiros de negócio que já constroem juntos e que agora abrem essa experiência a outros empresários."
- **Ponte:** à esquerda "Portugal" com Cila Santos e Bruno Rosado; ao centro a faixa Mar Largo vertical com a etiqueta "HM Negócios" num rectângulo calcário que a atravessa; à direita "Brasil" com Paulo Kazaks.
- **Manifesto:** "Sócios. Empresários. Dois países. Uma visão de crescimento."
- **Quem é Paulo Kazaks?** "Empresário brasileiro, parceiro de negócios de Cila Santos e Bruno Rosado e sócio dos dois na HM Negócios. Paulo representa o lado brasileiro desta parceria. Sua experiência como empresário e sua ligação a diferentes projetos e negócios tornam essa relação coerente com o conceito da formação: criar, conectar e expandir negócios para além de uma única área ou mercado. É Paulo quem abre as portas no Brasil para este encontro e recebe Cila e Bruno na BE Factory, reunindo empresários para uma formação dedicada a estratégia, crescimento e construção de ecossistemas."
- **Convite (bloco basalto, centrado):** "Paulo Kazaks convida" (cinza, 18px) / "Cila Santos & Bruno Rosado" (manifesto, calcário) / "Diretamente de Portugal para o Brasil."

### 09 Por que esta formação? (basalto)
```
┌──────────────────────────────────────────────────────────────────────┐
│ Chega um momento em que o próximo nível de um negócio já não         │
│ depende de vender mais do que já existe. (H2, colunas 1–9)           │
│ Depende de conseguir responder a perguntas diferentes:               │
│ ──────────────────────────────────────────────────────────────────── │
│ Que outros produtos podem nascer do que eu já construí?     (32px)   │
│ ──────────────────────────────────────────────────────────────────── │
│ Que novos canais posso criar?                                        │
│ ──────────────────────────────────────────────────────────────────── │
│ ... (5 perguntas)                                                    │
│ fecho                                                                │
└──────────────────────────────────────────────────────────────────────┘
```
- **H2:** "Chega um momento em que o próximo nível de um negócio já não depende de vender mais do que já existe."
- **Sub:** "Depende de conseguir responder a perguntas diferentes:"
- **Perguntas:**
  1. "Que outros produtos podem nascer do que eu já construí?"
  2. "Que novos canais posso criar?"
  3. "Que conhecimento posso transformar em uma nova área de negócio?"
  4. "Que ativos eu já tenho e ainda não estou aproveitando?"
  5. "Como posso criar novas receitas sem perder o foco da empresa principal?"
- **Fecho:** "É essa mudança de visão que permite deixar de pensar em um negócio e começar a pensar em um ecossistema."

### 10 O que você vai encontrar (calcário)
Lista de 7 linhas com filete: título H3 nas colunas 1–5 e descrição nas colunas 6–12. Sem números, porque não é uma sequência.
- **H2:** "O que você vai encontrar"

| Título | Descrição |
|---|---|
| Visão de ecossistema | Deixar de olhar para a empresa apenas como um produto ou serviço. |
| Identificação de oportunidades | Entender que novas áreas podem surgir dos ativos que o negócio já possui. |
| Novos produtos e serviços | Criar soluções que façam sentido dentro da estrutura e da marca. |
| Novos canais | Descobrir novas formas de chegar ao mercado e ao cliente. |
| Novas fontes de receita | Diversificar o faturamento sem criar negócios desconectados. |
| Estrutura e gestão | Preparar a empresa para suportar o crescimento. |
| Expansão | Pensar para além do mercado onde o negócio começou. |

### 11 Para quem é (calcário)
Duas colunas: "É para você se" (fundo basalto) e "Não é para você se" (filete basalto).
> Texto proposto por mim a partir da "Direção de comunicação" do PDF. O PDF não traz o texto desta secção.
- **H2:** "Para quem é"
- **Lead:** "Não é uma formação para começar um negócio. É um encontro para empresários que já construíram algo e querem descobrir como multiplicar essa estrutura."
- **É para você se:**
  - Você já tem um negócio funcionando e faturando.
  - Sente que o próximo passo não vem só de vender mais do mesmo.
  - Quer criar novos produtos, canais e receitas sem perder o foco da empresa principal.
  - Quer aprender com quem já construiu um ecossistema na prática.
- **Não é para você se:**
  - Você ainda está planejando abrir o primeiro negócio.
  - Procura teoria sem aplicação ou fórmulas prontas.

### 12 Informações práticas (basalto)
```
┌──────────────────────────────────────────────────────────────────────┐
│ Informações práticas (H2)                                            │
│  20      08      14      32                                          │
│  dias    horas   min     seg     ← contador (Archivo 68%, 96px)      │
│ ──────────────────────────────────────────────────────────────────── │
│ Data            Horário            Formato          Local            │
│ 20 de outubro   A partir das 10h   Presencial       BE Factory       │
│ Cidade          Término                                              │
│ São Paulo       [a confirmar]                                        │
└──────────────────────────────────────────────────────────────────────┘
```
- **Contador:** até `2026-10-20T10:00:00-03:00` (São Paulo, sem horário de verão). Depois dessa hora mostra "O encontro já começou."
- **Dados confirmados (PDF):** Data "20 de outubro de 2026"; Horário "A partir das 10h00"; Formato "Presencial"; Local "BE Factory"; Cidade "São Paulo, Brasil".
- **Por confirmar (PDF, ponto 12):** Término, com a etiqueta "a confirmar" (filete tracejado em cinza).
- **Investimento e vagas não aparecem na página** (decisão do Diogo em 29/09/2026).

### 13 Perguntas frequentes (calcário)
Acordeão (shadcn), colunas 1–8. Uma pergunta aberta de cada vez.
1. **Para quem é esta formação?** Para empresários que já têm um negócio funcionando e querem transformá-lo em uma estrutura capaz de gerar novos produtos, canais e fontes de receita.
2. **Quando e onde acontece?** No dia 20 de outubro de 2026, a partir das 10h00, na BE Factory, em São Paulo.
3. **É presencial ou online?** Presencial.
4. **Quem conduz a formação?** Cila Santos e Bruno Rosado, empresários e CEOs vindos de Portugal, a convite de Paulo Kazaks, sócio dos dois na HM Negócios.
5. **A que horas termina?** `[a confirmar]`
6. **Há certificado, coffee break ou estacionamento?** `[a confirmar]`

### 14 Encerramento (`#encerramento`, fundo Mar Largo em página inteira)
Sem formulário e sem botão: a página fecha repetindo a tese e o encontro.
```
┌──────────────────────────────────────────────────────────────────────┐
│≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈ calçada Mar Largo (estática) ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ ┌───────────────────────────────────────────────┐ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ │ (basalto)                                     │ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ │ Paulo Kazaks convida Cila Santos & Bruno R.   │ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ │ Seu negócio já funciona.                      │ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ │ Agora ele precisa se multiplicar.  (H2 largo) │ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ │ 20 de outubro de 2026 │ A partir das 10h00 │  │ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ │ BE Factory, São Paulo                         │ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
│≈≈ └───────────────────────────────────────────────┘ ≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈≈│
└──────────────────────────────────────────────────────────────────────┘
Cartão basalto: colunas 1–8, raio 4px, padding de 64px (desktop) / 32px (mobile). Mobile: cartão com largura total sobre a onda.
```
- **Linha de convite:** "Paulo Kazaks convida Cila Santos & Bruno Rosado" (como no hero).
- **Título (H2, largura 125%):** "Seu negócio já funciona. Agora ele precisa se multiplicar."
- **Informações:** "20 de outubro de 2026" (brasa) | "A partir das 10h00" | "BE Factory, São Paulo".

### Footer (basalto)
"Negócios Sem Fronteiras" / "20 de outubro de 2026 | BE Factory, São Paulo" / "Conheça o ecossistema: HN Hit Nails | Cila Santos | Elite Mind Business | Fluxus" (noutro separador) / "Uma iniciativa HM Negócios" / "© 2026" (sem link de política de privacidade: retirado a pedido do Diogo em 30/09/2026, porque a página não recolhe dados).

---

## 8. Página informativa (sem inscrição)

- **Decisão do Diogo em 29/09/2026:** a LP é só informativa. Não há botões de inscrição, formulário, barra fixa nem pergunta "Como faço minha inscrição?".
- O percurso continua a fechar no encontro: contador real até à data e hora, informações práticas e encerramento com data e local.
- Autoridade: parceria, bios e ecossistema real com links de prova.
- Sem menu de navegação. Os únicos links externos são os 4 do ecossistema (secção 06 e footer), sempre noutro separador.

## 9. Acessibilidade e performance

- Contrastes da secção 2 verificados. Foco visível com contorno de 2px (basalto em fundo claro, calcário em fundo escuro) e offset de 3px.
- `prefers-reduced-motion` respeitado. HTML semântico (um só `h1`). Acordeão acessível (Radix).
- `<html lang="pt-BR">`, título "Negócios Sem Fronteiras | 20 de outubro, São Paulo", meta description e tags OG.
- Fontes com `preconnect` e `display=swap`. Imagens com `loading="lazy"`, excepto a do hero. Metas: LCP < 2,5s, CLS < 0,1.

## 10. Stack no Lovable

React + Vite + TypeScript + Tailwind + shadcn/ui (Accordion), framer-motion, lucide-react. Uma só página, com secções com `id`. Tokens da secção 2 em CSS variables e no `tailwind.config`.

## 11. Por confirmar antes de publicar

| Tema | Estado |
|---|---|
| Hora de término | O PDF manda confirmar. Fica como "a confirmar" |
| Valor da inscrição e número de vagas | Retirados da página (decisão do Diogo em 29/09/2026) |
| URLs oficiais das 4 marcas | Pus as que encontrei na web (tabela da secção 06). Falta confirmação oficial |
| Endereço final e acesso à BE Factory | Não publicado. Encontrei uma morada pública da empresa, mas não a uso sem confirmação |
| Estacionamento, coffee break, certificado | A confirmar |
| Processo de inscrição | Fora desta versão: a LP é só informativa (decisão de 29/09/2026). O Lovable Cloud ficou activado no projecto, mas sem tabelas nem dados |
| Foto do Paulo Kazaks | Recebida (29/09/2026) |
| Foto individual do Bruno | O Diogo diz que a carregou no Lovable (29/09/2026). Às 17:45 ainda não estava nos ficheiros do projecto |
| Logótipos das marcas | Não recebidos. As marcas aparecem só em texto |
| Grafia "Kazaks" | **Confirmado pelo Diogo em 29/09/2026:** "Kazaks". A imprensa escreve "Kazak", mas não se usa |
| "HM Negócios" | **Confirmado pelo Diogo em 29/09/2026:** "HM Negócios" |
| Texto de "Para quem é" | Proposto por mim. O PDF não o traz |

## 12. Fontes consultadas

- PDF "Estudo_LP_Formacao_Brasil_Cila_Bruno.pdf": todo o conteúdo e a estrutura.
- https://pt.wikipedia.org/wiki/Mar_largo e https://pt.wikipedia.org/wiki/Calçadão_de_Copacabana: origem do padrão.
- https://www.nationalgeographicbrasil.com/meio-ambiente/2022/12/pau-brasil-qual-e-sua-historia-e-importancia e https://www.brasilianaiconografica.art.br/artigos/24251/os-nomes-da-arvore-vermelha-que-batizou-o-brasil: pau-brasil.
- https://www.elitemindbusiness.com: fundadores e ligação à Fluxus.
- https://fluxus.elitemindbusiness.com: responde HTTP 200 (verificado).
- https://www.hnhitnails.com e https://www.cilasantos.com: sites das marcas.
- https://www.brazilbeautynews.com/paulo-kazak,103 e https://www.linkedin.com/in/paulokazaks/: grafia do nome.

---

## Apêndice A: componente `CalcadaWaves.tsx`

Onda Mar Largo com textura de pedras (juntas irregulares, determinísticas, com seed 1849, o ano do Rossio). O comprimento de onda (384) é múltiplo do tile de pedras (96), por isso o deslize é contínuo, sem costuras.

```tsx
import { useId, useMemo } from "react";
import { motion, type MotionValue } from "framer-motion";

type Props = {
  className?: string;
  length?: number;      // comprimento da faixa no sentido das ondas (viewBox)
  depth?: number;       // profundidade da faixa (viewBox)
  band?: number;        // espessura de cada faixa de pedra
  wavelength?: number;  // múltiplo de 96, para o deslize não ter costura
  amplitude?: number;
  stones?: number;      // pedras por tile de 96
  dark?: string;
  light?: string;
  shift?: MotionValue<number>; // deslize ao longo das ondas (0 → -wavelength)
  vertical?: boolean;   // ondas a correr de cima para baixo (faixa vertical)
};

function mulberry32(seed: number) {
  return () => {
    seed |= 0; seed = (seed + 0x6d2b79f5) | 0;
    let t = Math.imul(seed ^ (seed >>> 15), 1 | seed);
    t = (t + Math.imul(t ^ (t >>> 7), 61 | t)) ^ t;
    return ((t ^ (t >>> 14)) >>> 0) / 4294967296;
  };
}

export function CalcadaWaves({
  className, length = 1920, depth = 360, band = 40, wavelength = 384, amplitude = 28,
  stones = 5, dark = "#1B1A18", light = "#F2EFE9", shift, vertical = false,
}: Props) {
  const uid = useId().replace(/:/g, "");
  const TILE = 96;
  const { waves, mortar } = useMemo(() => {
    const n = stones, s = TILE / n, rnd = mulberry32(1849);
    const jit = Array.from({ length: n }, () =>
      Array.from({ length: n }, () => [(rnd() - 0.5) * s * 0.44, (rnd() - 0.5) * s * 0.44]));
    const P = (i: number, j: number) => {
      const [dx, dy] = jit[((i % n) + n) % n][((j % n) + n) % n];
      return `${(i * s + dx).toFixed(1)} ${(j * s + dy).toFixed(1)}`;
    };
    let mortar = "";
    for (let i = 0; i < n; i++) for (let j = 0; j < n; j++)
      mortar += `M${P(i, j)}L${P(i + 1, j)}L${P(i + 1, j + 1)}L${P(i, j + 1)}Z`;
    // (u = ao longo das ondas, v = profundidade); na vertical troca-se para (v, u)
    const pt = (u: number, v: number) => (vertical ? `${v.toFixed(1)} ${u}` : `${u} ${v.toFixed(1)}`);
    const vAt = (u: number, v0: number) => v0 + amplitude * Math.sin((2 * Math.PI * u) / wavelength);
    const waves: string[] = [];
    for (let v0 = -band * 2; v0 < depth + band * 2; v0 += band * 2) {
      const a: string[] = [], b: string[] = [];
      for (let u = -wavelength; u <= length + wavelength * 2; u += 8) {
        a.push(pt(u, vAt(u, v0)));
        b.unshift(pt(u, vAt(u, v0 + band)));
      }
      waves.push(`M${a.join("L")}L${b.join("L")}Z`);
    }
    return { waves, mortar };
  }, [length, depth, band, wavelength, amplitude, stones, vertical]);

  const vbW = vertical ? depth : length;
  const vbH = vertical ? length : depth;
  const spanU = length + wavelength * 3;
  const cover = vertical
    ? { x: 0, y: -wavelength, width: depth, height: spanU }
    : { x: -wavelength, y: 0, width: spanU, height: depth };
  const motionStyle = shift ? (vertical ? { y: shift } : { x: shift }) : undefined;

  return (
    <svg viewBox={`0 0 ${vbW} ${vbH}`} preserveAspectRatio="xMidYMid slice" className={className}
      aria-hidden="true" focusable="false" style={{ display: "block", width: "100%", height: "100%" }}>
      <defs>
        <pattern id={`m-${uid}`} width={TILE} height={TILE} patternUnits="userSpaceOnUse">
          <path d={mortar} style={{ fill: "none", stroke: light }} strokeWidth={1.4} strokeLinejoin="round" />
        </pattern>
        <pattern id={`s-${uid}`} width={TILE} height={TILE} patternUnits="userSpaceOnUse">
          <path d={mortar} style={{ fill: "none", stroke: dark }} strokeWidth={1.1} strokeLinejoin="round" opacity={0.1} />
        </pattern>
      </defs>
      <rect width={vbW} height={vbH} style={{ fill: light }} />
      <motion.g style={motionStyle}>
        <rect {...cover} fill={`url(#s-${uid})`} />
        <g style={{ fill: dark }}>{waves.map((d, i) => <path key={i} d={d} />)}</g>
        <rect {...cover} fill={`url(#m-${uid})`} />
      </motion.g>
    </svg>
  );
}
```

Uso no hero (deslize ligado ao scroll):
```tsx
const heroRef = useRef<HTMLElement>(null);
const { scrollYProgress } = useScroll({ target: heroRef, offset: ["start start", "end start"] });
const reduce = useReducedMotion();
const waveX = useTransform(scrollYProgress, [0, 1], [0, reduce ? 0 : -384]);
// ...
<div className="h-[140px] md:h-[180px]"><CalcadaWaves depth={220} shift={waveX} /></div>
// Faixa vertical da parceria (secção 07): <div className="w-[120px] self-stretch"><CalcadaWaves vertical length={960} depth={240} /></div>
```

---

## Adenda 01/10/2026 — inscrição paga (substitui a decisão de 29/09 de LP só informativa)

Decisões do Diogo, a partir do feedback do Nelson (agência):
- **Inscrição paga:** R$ 300, por Stripe Checkout da Cila Santos (conta portuguesa), com cartão e Pix. Boleto não existe para contas portuguesas ([docs.stripe.com/payments/boleto](https://docs.stripe.com/payments/boleto)).
- **IOF do Pix (3,5%):** pago pelo comprador (`amount_includes_iof: "never"`) ([docs.stripe.com/payments/pix](https://docs.stripe.com/payments/pix)).
- **Faturação brasileira:** pessoa física (CPF) ou jurídica (CNPJ + razão social), com endereço e CEP. A Stripe aceitou o `br_cpf` no Customer, verificado no teste.
- **Aviso de pagamento à equipa:** feito pela Stripe (dashboard), para miriam.peixe@hnhitnails.com.
- **WhatsApp flutuante:** +351 927 250 911, com mensagem pré-escrita. O glifo verde é a única excepção à paleta.
- **Voltam:** os CTAs "Quero garantir minha inscrição", a barra fixa no mobile ("R$ 300 | 20 out"), o investimento nas informações práticas e as perguntas do FAQ sobre investimento, inscrição e pagamento. As vagas continuam fora.

Percurso técnico (Lovable):
1. Formulário (`#inscricao`).
2. `createInscricao`: valida no servidor, bloqueia email já pago, grava 'pendente' e cria o Customer e a Checkout Session.
3. Webhook `/api/public/stripe-webhook`: verifica a assinatura e é o único que marca 'pago'. Procura a linha por `inscricao_id` e pelo session id, e responde 500 em erro de base de dados. Sessão desta formação sem linha: 500 (a Stripe reenvia), excepto em `checkout.session.expired`, que responde 200 "ok" (sem pagamento, nada a perder; commit Lovable `66eb3d5`).
4. `/inscricao/sucesso`: só lê.

Teste de ponta a ponta em modo de teste, 01/10/2026, feito pelo agente do Lovable e verificado no histórico:
- pagamento com cartão 4242 → linha `pago`, `card`, `pago_em` 10:48:17 UTC, sessão `cs_test_…`;
- a mesma submissão repetida → bloqueada com "Este e-mail já tem uma inscrição paga…", 5 linhas antes e 5 depois.

Incidente (01/10/2026, cerca das 10:00): a primeira chave guardada no projecto era real (`rk_live_`). Um teste do agente criou na conta real da Cila um cliente "Teste Silva" e uma sessão de checkout por pagar. Sem cobrança. A seguir, `getStripe` passou a aceitar só chaves de teste.

Passagem a live (01/10/2026, 11:06, pedido do Diogo no Lovable "passar o stripe api para o live"): a guarda de teste foi retirada (commit Lovable `0761b71`) e `getStripe` aceita chaves live e de teste. A chave do projecto é `rk_live_`. Teste live sem cobrança às 11:59:
- inscrição no site publicado → linha 'pendente' e sessão `cs_live_…` de R$ 300 (cartão e Pix);
- a sessão foi expirada pela API e o webhook live pôs a linha em 'expirado' em menos de 30 s;
- limpeza: o cliente de teste foi apagado na Stripe (`deleted: true`); a linha foi copiada para `inscricoes_backup_teste_20261001` (que fica com 6 linhas) e depois apagada. `inscricoes` ficou com 0 linhas.

Ainda sem teste live: um pagamento concluído (linha 'pago'), um Pix real, os recibos e os avisos à Miriam.

Webhook live, 01/10/2026 (tarde). Horas em UTC; o painel da Stripe mostra hora de Lisboa (+1):
- **Pix:** a configuração de métodos de pagamento da conta (`pmc_1TIx1Q…`) tem cartão e Pix disponíveis e ligados (leitura pela API). A chave não tem "Accounts Read" e não precisa.
- **Sessão do "Teste Silva" esquecida:** `cs_live_a1y4slq…`, criada às 10:04:40 pela pré-visualização (cancel_url `localhost:8080`), ficou aberta depois de a linha ter sido apagada. Ao caducar, o webhook ia responder 500 ("Inscrição não encontrada") e a Stripe ia reenviar durante dias. Correcção `66eb3d5` (ver o passo 3 acima). A sessão foi expirada pela API às 13:09.
- **Webhook duplicado:** havia dois endpoints live para o site (`we_1ULiOnRc…` e `we_1ULiabRc…`), cada um com o seu segredo; o site só guarda um, por isso um deles falhava sempre. O Diogo apagou `we_1ULiOnRcs4np9RsbtCTyKNVs` às 13:17:44 (log da Stripe). Fica só `we_1ULiabRcs4np9RsbovxazELp` ("charismatic-legacy"). O `STRIPE_WEBHOOK_SECRET` foi regravado às ~13:22 com o segredo deste e o site republicado.
- **Entregas nesse endpoint** (separador "Entregas de eventos"): 11:59:50 200 OK (teste live); 13:09:10 e 13:09:26 500 (código antigo ainda publicado); 13:26:45 **200 "ok"**, reenvio manual do evento `evt_1ULjjURcs4np9RsbMPb9yJOT` com a correcção activa. O segredo bate certo: com o segredo errado a resposta seria 400.
- **Outros webhooks na mesma conta Stripe:** `www.belessa.pt/api/stripe/webhook` e uma função Supabase (`sqpkufmyijozyannxjts`). Ambos recebem `checkout.session.completed` de todos os pagamentos da conta, incluindo as inscrições desta formação. Não se sabe se ignoram pagamentos que não são deles.

Antes de abrir inscrições reais:
- termos e política de privacidade: os textos já estão no site (/termos e /privacidade, versão provisória de 01/10/2026). Falta fechar os 10 pontos "a confirmar" (8 nos termos, 2 na privacidade) e a revisão jurídica;
- ~~chave live com as permissões certas, webhook live no URL publicado ou no domínio próprio, e retirar a guarda de teste~~ **Feito a 01/10/2026:** chave `rk_live_`, webhook live em `https://hm-negocios.lovable.app/api/public/stripe-webhook` com os 4 eventos, guarda retirada. Com o domínio próprio, o webhook tem de passar para o novo endereço;
- na Stripe live: Pix activo, recibos por email ao cliente, acesso e notificações da Miriam;
- nota fiscal: quem emite;
- ~~limpar as linhas de teste da tabela `inscricoes`~~ **Feito a 01/10/2026:** 5 linhas apagadas (4 pendentes, 1 paga de teste). Cópia em `inscricoes_backup_teste_20261001` na base de dados; a tabela ficou com 0 linhas.
- ~~apagar o cliente "Teste Silva" na Stripe live~~ **Feito pelo Diogo a 01/10/2026.**
- domínio próprio;
- confirmar com quem gere os webhooks da Belessa e da função Supabase que ignoram os pagamentos desta formação.

### 01/10/2026 — formulário: dados perdidos no carregamento
- **Sintoma:** no teste do agente, os campos preenchidos de forma automática logo ao abrir a página ficaram vazios.
- **Causa provável:** valores introduzidos antes de o React assumir o formulário (página SSR) eram descartados.
- **Correcção (commit Lovable `a1750e0`):**
  - ao montar, o formulário recupera do DOM os valores já escritos, com as mesmas máscaras;
  - todos os campos passam a ter `name`, mais `autoComplete` na UF e na razão social;
  - o WhatsApp colado com "+55" fica sem o indicativo.
- **Teste sem submissão e sem Stripe:** passou em 2 corridas seguidas. Uma primeira corrida, durante a recompilação do servidor, falhou.

---

## Adenda 08/10/2026 — página interna `/admin` (inscrições e pagamentos)

Pedido do Diogo: uma página onde a Miriam veja as inscrições e se foram pagas na Stripe.

Feita pelo agente do Lovable em dois commits: `4ad69bc` (página) e `da736d7` (consultas à Stripe em lotes, etiqueta do Pix, filtros e textos da entrada). **Publicada pelo Diogo a 08/10, entre as 10:37 e as 10:41 UTC:** às ~10:37 `https://hm-negocios.lovable.app/admin` respondia 404; às 10:41 o pedido de acesso do Diogo já veio do site publicado (registo da autenticação), e a página responde 200 com "noindex, nofollow". O preview continua a responder 401 a quem não tem sessão no Lovable.

**Acesso**
- Só dois emails: `miriam.peixe@hnhitnails.com` e `diogo.monteiro@hnhitnails.com`. A lista está em `src/lib/admin.server.ts`, só no servidor. Para dar ou tirar acesso, muda-se esse ficheiro.
- Sem password: a pessoa escreve o email e recebe um código, que escreve na página. **Desde 08/10 (commits Lovable `5ec79bf` e `84108dc`) o código é enviado pelo nosso próprio SMTP**, e não pelo Lovable (ver "Envio por SMTP" abaixo). A 1.ª versão usava o envio do Lovable, com link, e esse email não chegou.
- Registo público desligado e entrada por email ligada na autenticação (alterações feitas pelo agente). As contas dos dois emails são criadas pelo servidor no primeiro pedido. Antes desta alteração não havia contas (`auth.users` = 0, consulta de 08/10), por isso nada que já existisse deixou de funcionar.
- Os dados chegam por funções de servidor que validam o token e o email antes de ler com a service role. A tabela `inscricoes` continua com RLS e sem políticas (0 políticas, consulta de 08/10).

**O que mostra**
- Todas as linhas de `inscricoes`, sem esconder nem juntar nenhuma. Se um email tiver mais de uma linha, aparece "Este email tem N inscrições".
- Duas colunas de pagamento, porque respondem a perguntas diferentes:
  - **Estado no site:** a coluna `status`, que só o webhook altera.
  - **Pagamento na Stripe:** consulta em directo de cada Checkout Session pelo id gravado na linha (`retrieve`, nunca `list`, porque a conta tem pagamentos de outros negócios). Etiquetas: Pago, Reembolsado, Reembolsado em parte, Em disputa, A aguardar Pix, Pix não pago, Checkout aberto, Expirou sem pagamento, Sem sessão Stripe e Erro ao consultar.
- "Não bate certo" (a vermelho) quando o site diz pago e a Stripe não diz Pago, ou o contrário. A página só mostra, não corrige.
- Resumo com a forma de contagem ao lado de cada número. Filtros: Todas, Pagas no site, Por pagar no site, Pagas na Stripe e Não batem certo. Horas em hora de Lisboa.
- Detalhe de cada linha: CPF/CNPJ, razão social, morada, consentimento, ids da Stripe e link para o pagamento no painel da Stripe.
- As consultas à Stripe vão em lotes de 20 inscrições por chamada, porque o site corre na Cloudflare (cabeçalho `server: cloudflare`) e cada chamada tem um limite de pedidos.

**Verificações**
- A chave live lê uma Checkout Session com `payment_intent.latest_charge` e lista PaymentIntents com `latest_charge`: as duas leituras deram "ok" no teste só de leitura do agente do Lovable, a 08/10. É a mesma leitura que o webhook faz quando há um pagamento. Fica assim fechada a dúvida de a chave restrita não ter acesso às cobranças.
- Entrada testada pelo agente só com um email fora da lista: mostra a mensagem neutra e não envia nada.
- **Por testar:** a entrada com um email autorizado (é preciso receber o email), a lista com sessão iniciada e a verificação na Stripe com dados reais.
- Estado da tabela a 08/10: 1 linha, que é o teste do Diogo de 01/10 (`expirado`). Ainda não há inscrições reais.

**Alteração que não foi pedida:** no commit `4ad69bc`, o `package.json` fixou `@lovable.dev/vite-tanstack-config` em `2.25.3` (antes `^2.24.0`). Deve ter vindo da plataforma. Afecta a build do site todo e só se nota ao publicar.

**Para a Miriam usar**
1. ~~Publicar o site~~ **Feito pelo Diogo a 08/10** (ver acima). Antes de publicar, os termos já tinham o texto final de 01/10 (verificado em `/termos`), por isso a publicação só juntou os dois commits de hoje e a alteração do `package.json`.
2. O Diogo testa primeiro. **1.º teste, 08/10, 10:41 UTC: o email não chegou.**
   - Correu bem até ao serviço de envio. A conta foi criada às 10:41:12 (`auth.users`) e o link foi gerado às 10:41:13 (`recovery_sent_at`, token em `auth.one_time_tokens`). No registo da autenticação, `/otp` deu 200 e a entrega ao serviço de envio do Lovable deu `"Hook ran successfully"` (`api.lovable.dev/.../backend/email-hook`).
   - Depois disso não há registo: o projecto não tem domínio de email próprio, e o histórico de envios do Lovable só cobre domínios próprios. O remetente é um endereço padrão do Lovable, num domínio do Lovable (o endereço exacto não aparece nos registos).
   - Causa provável, não verificada: retenção no filtro anti-spam do domínio (`mx1/mx2.cleanmx.pt`) ou na pasta de spam. **O email da Miriam está no mesmo domínio e no mesmo filtro.**
   - Opção oferecida pelo Lovable: um domínio de envio próprio (ex.: `notify.hnhitnails.com`, com delegação NS no DNS, só em planos pagos). **O Diogo escolheu outra: SMTP com uma conta de email que já tem** (ver abaixo).
3. Criar os 5 secrets SMTP no Lovable, publicar e voltar a testar (ver "Envio por SMTP").

**Envio por SMTP (08/10/2026, decisão do Diogo)**
- A autenticação do Lovable não aceita SMTP próprio: a configuração da autenticação do projecto não tem campos de SMTP, segundo o agente do Lovable e a documentação em docs.lovable.dev/features/custom-emails. Por isso o envio passou a ser feito pelo nosso código:
  1. a conta é procurada ou criada;
  2. verifica-se o limite de 1 email por minuto, guardado em `app_metadata.admin_code_sent_at`. Isto acontece **antes** de gerar o código, porque cada código novo anula o anterior (corrigido no `84108dc`);
  3. `auth.admin.generateLink({ type: "magiclink" })` devolve o código em `email_otp`, sem enviar email;
  4. o código vai por SMTP com a biblioteca `worker-mailer` (porta 465 com TLS, 587 com STARTTLS);
  5. a página confirma o código com `verifyOtp({ type: "email" })`.
- Os dados da conta ficam em 5 secrets do projecto: `SMTP_HOST`, `SMTP_PORT`, `SMTP_USER`, `SMTP_PASSWORD` e `SMTP_FROM`. Não estão no código nem no repositório. **A 08/10, às 11:07 UTC, ainda não estavam criados:** o Diogo cria-os no Lovable, na secção de Secrets do projecto.
- O código tem **8 dígitos** (configuração da autenticação). Os textos da página não indicam o número, e o campo aceita entre 6 e 8.
- Teste feito pelo agente do Lovable, sem email: `generateLink` + `verifyOtp` com a conta do Diogo funcionou. Deixou `last_sign_in_at` = 11:03:42 UTC na conta do Diogo (`auth.users`).
- **Por provar:**
  - o envio SMTP a partir do site publicado, que corre em Cloudflare Workers (preset `cloudflare-module`). No preview não funciona, porque o preview corre em Node;
  - a build de publicação com o `worker-mailer`.
  Os dois só se provam ao publicar e pedir o primeiro código.
- **Remetente:** o hnhitnails.com tem DMARC `p=reject` com alinhamento estrito, e o SPF autoriza a cleanmx, 94.46.175.209, 94.46.181.217, `a` e `mx` (DNS lido a 08/10). Um `SMTP_FROM` @hnhitnails.com tem de sair por um desses servidores. Uma caixa do alojamento do domínio cumpre isto.

**Testes do envio por SMTP no site publicado (08/10/2026, pedidos feitos por mim com o email do Diogo)**

| Hora UTC | Resultado | Fonte |
|---|---|---|
| 11:18 | Falhou: `admin smtp: falhou`, fase "autenticação" | logs do site publicado (agente do Lovable) |
| 11:38 | Falhou da mesma forma, depois de o Diogo corrigir os secrets | idem |
| 11:58 | Falhou da mesma forma (o Diogo encontrou a password errada) | idem |
| 12:59 | Falhou da mesma forma, depois de nova publicação | idem |
| 13:02 | Login de diagnóstico no ambiente do agente do Lovable (smtplib, porta 465, AUTH PLAIN LOGIN): **entrou** | resposta do agente |
| 13:51 | **Envio aceite:** `admin_code_sent_at` = 13:51:32 UTC na conta do Diogo | `auth.users` |

- O teste das 13:51 foi feito depois da publicação do commit `826135b`, que só muda o log (a mensagem do servidor de email passa a ficar registada, com os dados sensíveis trocados por "[oculto]").
- **Não se sabe porque falhou às 12:59 e funcionou às 13:51.** O código do envio é o mesmo. As hipóteses são:
  - a publicação das 12:59 ainda não tinha a password corrigida;
  - o fornecedor bloqueou temporariamente o login depois das tentativas falhadas.
  Se voltar a falhar, o log mostra agora a resposta exacta do servidor.
- Por confirmar pelo Diogo: se o email das 13:51 chegou à caixa, e a entrada completa (código, lista e coluna da Stripe).
