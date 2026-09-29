---
name: branding-borelli
description: "A identidade visual da Borelli Advocacia (Direito da Saúde, Fortaleza) no sistema Grifo Nosso v1: Azul Noite e Papel como campos, o Azul Borelli da marca, o ouro só sobre azul e o metal só dentro do logotipo, Newsreader nos títulos com UMA palavra grifada (marca-texto no claro, sublinhado dourado no azul), Lexend no texto, a linha, o losango e a trama tirados do símbolo, foto real sem luz colorida, as cinco leis da casa, o bloco de identificação da OAB, o selo de canais oficiais e as regras de publicidade da advocacia (Provimento 205/2021 e Código de Ética da OAB), motores de gráfico (bviz) e de forma (bforms). Use para qualquer material da Borelli Advocacia ou de Caico Borelli: post, carrossel, story, reels, WhatsApp, site, landing page, proposta de honorários, contrato, procuração, manual do cliente, apresentação, e-mail e impresso. Triggers: /branding-borelli, branding borelli, marca borelli, padrão borelli, identidade borelli, borelli advocacia, adv borelli, caico borelli, material da borelli, post da borelli, deck da borelli, grifo nosso."
---

# /branding-borelli · A identidade visual da Borelli Advocacia

Um estilo de casa travado, chamado **Grifo Nosso**. "Grifo nosso" é a expressão que todo advogado escreve depois de uma citação quando destaca o trecho que importa. A Borelli faz isso por quem a procura: lê o contrato, a negativa do plano e a regra da Agência Nacional de Saúde Suplementar (ANS) e aponta a parte que decide. No sistema, isso vira o recurso de assinatura: **em cada título, uma palavra recebe o grifo.** A Borelli fala como quem já passou pela negativa: **título sereno em serifa, campo azul ou papel claro, o ouro como linha fina e a palavra que decide grifada.** Cada peça explica, nenhuma oferece. Vale para **todo** material da Borelli Advocacia e de Caico Borelli.

Palavras-guia: clara, próxima, firme, honesta, sóbria. Nunca: gritada, triunfal, promocional, juridiquês, luxo genérico.

**Abra PRIMEIRO:** [`brand-book.html`](brand-book.html), o estilo documentando a si mesmo em 24 seções, com a marca, as fichas de cor, as escalas, os modelos de peça em tamanho real e as regras da OAB. O `<head>` e a `<style>` dele são o template portátil de **documento**. Para **apresentação**, o esqueleto pronto é [`deck-template.html`](deck-template.html). Os motores vivem em [`bviz.js`](bviz.js) (dados) e [`bforms.js`](bforms.js) (formas). Os snippets da marca, do bloco de identificação, do selo de canais oficiais e do e-mail estão em [`lockup.html`](lockup.html). Quando a peça parece com esses arquivos, está certa.

---

## Onde a skill roda (e o que muda em cada lugar)

| Ambiente | Onde instalar | O que muda |
|---|---|---|
| **Claude Code** (terminal, VS Code, app de desktop) | `~/.claude/skills/branding-borelli` | Nada. Ambiente completo: escreve arquivo, usa `assets/`, exporta PDF. |
| **Codex CLI** | `~/.codex/skills/branding-borelli` | Nada. |
| **claude.ai** (navegador e celular) | Settings, Capabilities, Skills (ZIP do Releases) | **O artefato é um arquivo só: não enxerga `assets/` nem os `.js`.** |

**REGRA DO NAVEGADOR (claude.ai):** todo HTML gerado ali é **autocontido**.
1. **Marca:** use os blocos em **data URI** do [`lockup.html`](lockup.html) (bloco 05, ouro; bloco 06, Azul Borelli; bloco 07, símbolo). Copie o `src` inteiro; nunca digite, resuma ou reconstrua um data URI.
2. **Fotos:** gere o data URI por código a partir do arquivo de `assets/fotos/`, sem alterar a imagem.
3. **Motores:** cole `bviz.js` e `bforms.js` dentro de um `<script>` do próprio arquivo.
4. **Fontes:** continuam pelo link do Google Fonts.
5. **PDF:** entregue o HTML e mande imprimir pelo Chrome (seção "Exportar PDF").

**Para ENVIAR um HTML a alguém**, use sempre a versão autocontida: `python3 autocontido.py <arquivo.html>` grava em `dist/` com imagens, fontes e motores embutidos. As versões prontas do brand book, da apresentação e das assinaturas já estão em `dist/`.

## Cores (TRAVADAS)

O sistema **não tem modo escuro automático**: a cor é da marca. `body` sempre com background explícito e `color-scheme: light`.

**Dois campos.** **Azul Noite** para o que chama atenção (capa, abertura, redes, topo do site, story). **Papel** para o que se lê com calma (miolo de carrossel, documento, página de conteúdo, manual do cliente, proposta). **Névoa** alterna com o Papel. **Azul Borelli** (a cor do logotipo) é também campo secundário. **Abismo** fecha rodapés. Branco puro só em documento jurídico impresso.

| Token | Nome | HEX | Origem | Uso |
|---|---|---|---|---|
| `--noite` | Azul Noite | `#172B3D` | landing page 2026 | campo escuro principal; título sobre claro |
| `--marinho` | Azul Borelli | `#244460` | **logotipo de 2024 (medido)** | a cor da marca: logotipo, botão, link e ícone no claro; campo secundário |
| `--abismo` | Abismo | `#0F1D2A` | extensão | rodapé, capa profunda, sombra de leitura |
| `--mare` | Maré | `#1E354B` | extensão | painel sobre Noite |
| `--ouro` | Ouro Borelli | `#C9A24D` | logotipo de 2026 e landing page | linha, rótulo, numeral e grifo **sobre azul**; botão cheio sobre Noite (texto Noite) |
| `--metal` | Ouro metálico | `linear-gradient(90deg,#A88545 0%,#D7B970 28%,#ECD282 52%,#CCAB60 74%,#AA8542 100%)` | logotipo de 2026 | **só dentro do arquivo da marca**. Nunca em texto, fundo, botão ou moldura |
| `--champanhe` | Champanhe | `#EBD081` | pico do degradê | rótulo e numeral **sobre Azul Borelli**; link sobre Noite |
| `--papel` · `--nevoa` · `--branco` | Papel · Névoa · Branco | `#F7F9FB` · `#E1ECF5` · `#FFFFFF` | landing page 2026 | campo de leitura · faixa e painel claros · documento jurídico |
| `--gelo` · `--bruma` | Gelo · Bruma | `#DCE6EF` · `#AEBCCB` | extensão | texto e apoio sobre azul |
| `--grafite` · `--pedra` | Grafite · Pedra | `#3F4A56` · `#5B6875` | landing page 2026 | texto e apoio sobre claro |
| `--grifo` | Grifo | `#FFE9A8` | marca-texto | o grifo no claro; nunca fundo de bloco |
| `--bronze` | Bronze | `#7A5A1E` | extensão | o dourado quando precisa ser TEXTO no claro (raro) |
| `--linha-clara` · `--linha-escura` | Linhas | `#DFE7EE` · `#2A4057` | extensão | linhas de 1 px |
| `--erro` · `--ok` | Estados | `#B42318` · `#1E7B4F` | extensão | formulário, sempre com texto e ícone |

**Pares de leitura (WCAG):** branco/Noite 14,5 · gelo/Noite 11,5 · bruma/Noite 7,5 · ouro/Noite 6,0 · champanhe/Noite 9,6 · branco/Azul Borelli 10,1 · champanhe/Azul Borelli 6,7 · Noite/Papel 13,7 · grafite/Papel 8,6 · Azul Borelli/Papel 9,6 · pedra/Papel 5,4 · Noite/Névoa 12,1 · Noite/Grifo 12,1 · Noite sobre ouro 6,0. **Proibidos:** ouro sobre Papel, Névoa ou branco (2,3); branco sobre ouro (2,4); ouro em texto pequeno sobre Azul Borelli (4,2: use champanhe); o laranja antigo `#FFBC58` sobre branco (1,7). Texto sobre botão ouro é sempre Azul Noite.

**Orçamento do ouro (LEI I):** ouro chapado mais metal ocupam no máximo **5% da área** da peça e marcam **uma** informação. **Um único elemento metálico por peça** (o logotipo ou o símbolo). Proporção no conjunto das peças do mês: Noite 40 · Papel 30 · Névoa 12 · Azul Borelli 8 · Branco e gelo 5 · Ouro 4 · Grifo 1.

**Saem:** o laranja-dourado `#FFBC58` e o azul `#1D344E` do site de 2024; o azul royal `#1D3863` do Instagram; luz roxa e rosa nas fotos; degradê dourado em fundo. CMYK e Pantone dependem de prova de gráfica; metal no papel é hot stamping ou ouro chapado, nunca amarelo.

## Tipografia (TRAVADA)

```html
<link href="https://fonts.googleapis.com/css2?family=Newsreader:ital,opsz,wght@0,6..72,400;0,6..72,500;0,6..72,600;1,6..72,400;1,6..72,500&family=Lexend:wght@300;400;500;600&display=swap" rel="stylesheet">
```

| Papel | Fonte | Regras |
|---|---|---|
| Títulos, numerais, números grandes | **Newsreader 500** (600 em número e título curto na peça) | Serifa de leitura feita para a tela, já usada nos títulos da landing page de 2026. ≥ 26 px na peça (no documento, o intertítulo desce a 22 px no celular). Entrelinha 1,04 a 1,15. Caixa normal. `font-optical-sizing:auto`. |
| **O grifo** | a mesma fonte do título | **Uma** palavra ou expressão por título, marcada com `<em>`: no Papel, na Névoa e no branco, faixa de marca-texto `#FFE9A8` atrás da metade de baixo da palavra; no azul, sublinhado dourado fino. **Não é itálico.** |
| Citação, olho, termo latino | **Newsreader Italic 400** | Só em citação real, frase do fundador e expressão latina (procuração *ad judicia*). Nunca em parágrafo. |
| Texto, rótulo, botão, dado, legenda | **Lexend** 300 · 400 · 500 · 600 | Corpo 300 a partir de 16 px; 400 em 15 px ou menos e em botão; 500 em rótulo; 600 só em número de interface. Rótulo em caixa alta com `letter-spacing:.16em` (eco de ADVOCACIA ESPECIALIZADA). |

- **Escala do documento (tela/celular):** display 104/48 · título de seção 60/36 · subtítulo 38/27 · intertítulo 27/22 · chamada 21/18 · corpo 17/16 (entrelinha 1,68) · apoio 15 · legenda 13 · rótulo 11. Lexend só nesses corpos. `font-variant-numeric: lining-nums`.
- **Escala da peça 1080 px** (unidade `--u: calc(100cqw/1080)`): título 88 a 104 (máximo 3 linhas) · subtítulo 52 a 56 · chamada e corpo 32 a 36 · rótulo 26 (+0,16 em) · **piso absoluto de 26 px para qualquer texto, inclusive a identificação da OAB** (o post aparece a cerca de 36% no celular) · margem 72 · linha 2 a 3.
- **Legenda de reels:** Lexend 500 branca, 1 a 3 palavras por vez, na altura do peito, sem caixa; a palavra-chave com o grifo dourado (sublinhado) ou em Newsreader 600 a 1,15×.
- **Montserrat** existe só DENTRO do arquivo do logotipo. **Inter, Plus Jakarta Sans, Poppins, Raleway e Amiri saem.** Se Newsreader ou Lexend faltarem numa ferramenta: títulos em **Source Serif 4** (ou Georgia), texto em **Inter** (ou Arial).

## A marca (TRAVADA)

Não existe arquivo vetorial publicado pelo escritório (o site tem PNG de 289 × 63 de 2024 e WebP de 512 × 112 de 2026, que corta o último "I"; originais em `assets/referencia-original/`). As versões de `assets/` são a **reconstrução vetorial**: símbolo redesenhado na geometria exata (grade de 45°, módulo m, três losangos, moldura aberta e duas pontas; 95,4% de sobreposição com o publicado), palavra BORELLI vetorizada do arquivo de 2026 com o R de perna curva, linha de apoio composta com o espaçamento medido. Rótulo em material que apresenta a marca: "reconstrução vetorial · aguarda o arquivo original".

A marca é **sempre um arquivo** de `assets/`: nunca redesenhe, redigite "BORELLI" em fonte, recolora fora das versões, gire, estique, contorne, ponha em caixa branca sobre foto, aplique sombra, brilho ou relevo, ponha o metal sobre fundo claro, separe a linha de apoio ou use o arquivo antigo que corta o "I".

| Versão | Arquivo | Status | Fundo |
|---|---|---|---|
| Horizontal ouro metálico | `borelli-horizontal-ouro.svg` / `-web.png` / `.png` (e `-ouro-fundo`) | **Oficial** (reconstruída) | Azul Noite, Abismo, foto escura com sombra de leitura |
| Horizontal Azul Borelli | `borelli-horizontal-marinho.*` | **Oficial** (reconstruída) | Papel, Névoa, branco |
| Horizontal branca | `borelli-horizontal-branco.*` | Derivada | campo Azul Borelli, foto escura, vídeo |
| Ouro chapado | `borelli-horizontal-ouro-chapado.*` (e vertical, símbolo) | Derivada | bordado, carimbo, gravação, hot stamping |
| Azul Noite (uma cor) | `borelli-horizontal-noite.*` | Derivada | documento em uma cor, carimbo, cópia P&B |
| **Reduzida** (sem a linha de apoio) | `borelli-horizontal-sem-apoio-{ouro,marinho,branco,noite,ouro-chapado}.*` | Derivada | entre 100 e 200 px; reserva da pendência P2 |
| Vertical | `borelli-vertical-{ouro,marinho,branco,noite,ouro-chapado}.*` | Derivada | espaço estreito e alto |
| Símbolo | `borelli-simbolo-{ouro,marinho,branco,noite,ouro-chapado}.*` | Derivada | rodapé de peça, selo, tudo abaixo de 100 px |
| Avatar | `borelli-avatar.svg` / `-1080.png` / `-640.png` | Derivada | foto de perfil do escritório e do atendimento (símbolo ouro sobre Noite) |
| Favicon | `borelli-favicon.svg` / `-32` `-180` `-512.png` | Derivada | aba do navegador, atalho |
| Compartilhamento | `borelli-compartilhamento-1200x630.png` | Derivada | imagem do link do site |

Proporções para `width`/`height`: horizontal e reduzida **2589 × 565**; vertical **1913 × 1435**; símbolo **612 × 565**; avatar 1080 × 1080; favicon 512 × 512.

- **Respiro:** x = 1 módulo do símbolo (a meia-diagonal de um losango) = 17,7% da altura do símbolo. Na horizontal, x ≈ 3,9% da largura; na vertical, 5,3%; no símbolo sozinho, 16,4%.
- **Tamanho mínimo:** horizontal completa **200 px** na tela e **45 mm** no impresso (abaixo disso a linha "Advocacia Especializada" vira um risco); reduzida **100 px** e 25 mm; vertical **150 px** e 35 mm; símbolo **24 px** e 6 mm.
- **Na peça de 1080:** completa com no mínimo **560 u** (cerca de 200 px no celular), só na capa, na última lâmina e em peça institucional; rodapé com a **reduzida (360 u)** ou o **símbolo (88 u)**. Classes `.pc-marca`, `.pc-marca--reduzida`, `.pc-simbolo`.
- **O metal só vive sobre azul.** No claro, a marca é Azul Borelli.
- **Nome em texto:** primeira menção **"Borelli Advocacia"** (outras empresas de Fortaleza usam Borelli no nome); depois "a Borelli" ou "o escritório". A razão social **Caico Borelli Sociedade Individual de Advocacia** vai no bloco de identificação, no contrato, na procuração e no rodapé do site. Nunca "Morelli", "Borelli Advogados", BORELLI em caixa alta fora do logotipo.

## As cinco leis da casa (TRAVADAS)

1. **O dourado é da marca.** O metal vive no logotipo. Fora dele, o ouro é linha fina, rótulo e numeral sobre o azul e o grifo sobre o azul. No claro, o ouro nunca é texto. No máximo 5% da área.
2. **Um grifo por título.** Uma palavra ou expressão recebe o grifo: é a parte que decide. Se tudo é destaque, nada se destaca. Se falta espaço, corta-se texto, nunca margem.
3. **Informar, nunca oferecer.** Toda peça ensina algo (a regra, o documento, o prazo, o direito). Nenhuma oferece serviço ou convida a processar. O contato aparece como informação, nos canais oficiais.
4. **Gente de verdade, com autorização.** Só fotos reais do escritório, do Caico, dos advogados e da equipe, com autorização de imagem por escrito. Nada de banco de imagem, pessoa gerada por IA, corpo exposto, criança atendida ou cliente (nem com autorização).
5. **Nenhuma promessa, nenhuma comparação.** Sem resultado prometido ou comemorado, sem superlativo, sem número de processos ou taxa de êxito, sem preço, parcelamento, gratuidade ou "sem compromisso", sem caso concreto, print de decisão ou depoimento. Nome e OAB sempre que a regra pedir.

## Arquitetura de marca

| Marca | Papel | Assina com |
|---|---|---|
| **Borelli Advocacia** (marca-mãe, @borelli.advocacia) | conteúdo educativo, equipe, atendimento, canais oficiais | logotipo + bloco da sociedade; avatar = símbolo |
| **Caico Borelli** (marca pessoal, @caicoborelliadv) | autoridade, história de origem, comentário jurídico, bastidores | bloco do advogado (OAB/CE 24.895); o escritório entra como "Fundador da Borelli Advocacia"; retrato real |
| **Advogados com perfil próprio** (Thaís Cruz, OAB/CE 24.202; Yasmin, OAB/CE [nº]) | conteúdo da área de cada um | bloco do advogado; logotipo, fontes e redes oficiais obrigatórios |
| **Perfis de atendimento** (quem não é advogado) | responder quem procurou, compartilhar o conteúdo | "Atendimento Borelli Advocacia"; nunca "Dr." ou "advogado"; nunca abordar quem não pediu contato nem fazer análise jurídica |
| **Comunidades** ("Reparadora Legal", "Comunidade Barigata") e **séries editoriais** | relacionamento e conteúdo | nome em texto com "uma comunidade da Borelli Advocacia"; sem logotipo próprio até decisão |

Unidade em outro estado, se houver: marca-mãe com indicação regional em texto ("Borelli Advocacia · [estado]"), sem logotipo próprio, até decisão. Nunca assinar peça do escritório como se fosse do Caico, nem o contrário.

## Voz e tom

Clara (traduz o jurídico), próxima (de quem já passou pela negativa), firme (com a regra e com a operadora, nunca com a cliente), honesta (não promete prazo nem resultado; notícia boa ou ruim pelo mesmo canal), sóbria (OAB). Frase curta, verbo concreto, norma citada com número. Por escrito, **"você"** (o Caico pode falar "tu" nos vídeos dele).

- **Diga:** a regra, o documento, o prazo, "depende", "por escrito", "o que diz a norma", "cada caso é analisado individualmente".
- **Nunca:** vitória, conquista, garantido, especialista (sem título), referência, o melhor, o maior, líder, excelência, gratuito, sem compromisso, contrate, "foi negado? fale conosco", "me chama no direct", "Quero analisar meu caso" (em post e anúncio), "estética" para cirurgia reparadora.
- **Chamadas em três níveis** (Cartilha do Conselho Federal e Provimento 205/2021):
  1. **Conteúdo** (post, carrossel, reels, anúncio): só chamada educativa: "Salve para consultar depois" · "Compartilhe com quem está passando por isso" · "Mande sua dúvida para o próximo conteúdo" · "Leia o guia completo no site".
  2. **Contato como informação** (bio, rodapé, última lâmina, site): "Canais oficiais da Borelli Advocacia: [WhatsApp] · [site] · [e-mail]" e o botão "Fale com o escritório" (no formulário, "Enviar mensagem").
  3. **Atendimento** (quem já procurou ou já é cliente): "Envie seus documentos por aqui" · "Agende sua conversa de acompanhamento" · "Veja o manual do cliente".
- **Pontuação:** zero travessão; no máximo uma exclamação; nada de caixa alta longa; zero emoji na arte; em legenda e WhatsApp, só o 💙, no máximo um.

## Publicidade da advocacia (OAB) · TRAVADA

Base (conferida em 28/09/2026): Provimento 205/2021 do Conselho Federal da OAB e Anexo Único (vigente, sem alteração); Código de Ética e Disciplina da OAB (arts. 39 a 47-A); Estatuto da Advocacia, Lei 8.906/1994 (arts. 1º §3º, 3º-A, 14, 16 §4º, 34); Provimentos 112/2006 e 170/2016; Recomendação 001/2024 (IA); Resolução OAB/CE 02/2026; Cartilha do Conselho Federal (2024); LGPD. Detalhe, textos literais e fontes na seção 08 do brand book. **O manual adota sempre a leitura conservadora. Não substitui a análise ética do escritório nem uma consulta ao Tribunal de Ética e Disciplina da OAB/CE.**

**Bloco de identificação** (mesma fonte, mesmo tamanho, mesma cor; snippet no bloco 09 do `lockup.html`):
- Advogado: `Caico Borelli · Advogado · OAB/CE 24.895` (conferir no Cadastro Nacional dos Advogados antes de imprimir).
- Sociedade: `Caico Borelli Sociedade Individual de Advocacia · Registro OAB/CE [nº] · Responsável: Caico Borelli · OAB/CE 24.895`.
- **Onde:** bio; **dentro da peça** quando ela sai do perfil (WhatsApp, impresso, anúncio, vídeo patrocinado, compartilhamento); rodapé do site e da landing page; cartão; papel timbrado; proposta; contrato; assinatura de e-mail; placa. Na peça de 1080, nunca abaixo de 26 px. Número não confirmado sempre em `[nº]`.

**Aviso de publicidade:** "Conteúdo informativo. Não constitui promessa de resultado, prazo ou valor. Cada caso é analisado individualmente."

**Vedado em qualquer peça:** oferta de serviço e estímulo ao litígio; preço, parcelamento, gratuidade, desconto; "especialista" ou "especializada" sem título certificado; autoengrandecimento e comparação; promessa de resultado; divulgação de resultado, liminar, decisão, print, alvará, número de processo, caso concreto (mesmo com dados ocultos e com autorização), depoimento e lista de clientes; número de processos e taxa de êxito; ostentação da estrutura; mutirão com orientação gratuita; influenciador pago, comissão por indicação, parceria com clínica, médico, farmácia ou associação como canal de clientes; mensagem direta, WhatsApp ou e-mail para quem não pediu contato; mala direta; sorteio e prêmio; símbolo da OAB; outdoor, adesivo em carro, anúncio que interrompe vídeo; comprar seguidores.

**Zona cinzenta, leitura conservadora:** anos de experiência só como dado biográfico ("Inscrito na OAB/CE desde [ano]"); avaliações do Google (não pedir, não republicar, responder sem citar o caso); humor (tom leve sim; trend, dancinha e meme não; humor com doença, plano, juiz ou colega nunca); vídeo impulsionado só educativo; letreiro iluminado discreto; comentar caso da mídia pela tese, nunca pela atuação dos colegas; "Borelli Advocacia" como marca de sociedade unipessoal (pendência P1).

**IA e atendimento:** assistente automático se identifica como máquina, não responde consulta jurídica de quem não é cliente, oferece falar com uma pessoa; uso de IA com dados do cliente exige consentimento escrito (Recomendação 001/2024). **LGPD:** dado de saúde é sensível; formulário pede só o necessário, com aviso de privacidade; nada de público de remarketing a partir de páginas de doenças; foto do corpo recebida no atendimento nunca sai do atendimento; nunca criança atendida.

**Quem aprova:** o advogado responsável pela peça (o Caico nas peças do escritório e do perfil dele; cada advogado no próprio perfil). Quem publica responde pelo conteúdo, inclusive o feito por agência, freelancer ou IA.

**Selo de canais oficiais** (proteção contra o golpe do falso advogado): WhatsApp (85) [número oficial] · atendimento@advborelli.com.br · advborelli.com.br · @borelli.advocacia, com "Recebeu mensagem de outro número? Não responda e confirme por um destes canais." Vai na bio, no rodapé do site, no manual do cliente, na assinatura de e-mail e no perfil do WhatsApp (bloco 10 do `lockup.html`).

**Normas da ANS:** a RN 259/2011 foi revogada pela **RN 566/2022** (prazos de atendimento). Cite a norma em vigor, com número, depois de conferir no texto oficial.

## Fotografia

Só fotos reais (`assets/fotos/`): o Caico à mesa e na poltrona do escritório (tijolo, madeira, luz quente), diante da tela com a marca BORELLI, em palestras, e retratos de estúdio em fundo escuro. O acervo é de baixa resolução e parte dele tem **luz roxa ou rosa**: neutralize (receita na seção 09) ou não use. Texto sobre foto: sombra de Abismo subindo da base, nunca caixa colorida. Foto como janela: retângulo, linha fina a 12 px da imagem. Nunca banco de imagem, pessoa gerada por IA, cliente, corpo, criança, antes e depois, print de decisão, martelo ou balança como foto. A sessão de fotos (Caico e advogados com luz natural, mãos com documentos sem dado legível, atendimento por vídeo sem cliente identificável, retratos em fundo escuro limpo; lente 35 a 50 mm; 4:5 e 9:16; autorização por escrito) é pendência.

## Formas e dados

**`bforms.js`**: a ilustração da casa, tirada da geometria do símbolo (grade de 45°) sem imitar o logotipo. `<div class="forma-svg" data-bforms="losango"></div>` ou `bforms.render(el, 'percurso', opts)`. Formas: `linha` (régua, estrutura) · `losango` (foco, a parte que decide) · `elo` (dois losangos que se tocam: pessoa e direito) · `avanco` (o próximo passo) · `percurso` (as etapas do caso) · `trama` (textura de campo azul) · `grade45` (construção, método) · `moldura` (a janela da foto) · `grifo` (o destaque). Uma forma por peça, ao lado do texto, nunca atrás; a trama só em campo azul. **Clichês vedados:** balança, martelo de juiz, coluna grega, livro de leis, estátua da Justiça. `bforms.svg(nome, opts)` devolve o SVG para colar no Canva.

**`bviz.js`**: gráficos em SVG puro. `<div class="grafico-svg" data-bviz='{"tipo":"barras","rotulos":["A","B"],"valores":[7,14],"destaque":1}'></div>`. Tipos: `barras`, `barras-h`, `linha`, `composicao`, `anel`, `funil`, `fluxo`, `kpi`, `linha-tempo`, `cota`. Um destaque (ouro no azul, Azul Borelli no claro) marcado pelo losango, o resto neutro; título que já diz a conclusão; fonte e data sempre. **Nunca** número de processos, êxito, clientes, valores de condenação ou avaliações; número de norma só conferido; dado sem fonte leva "Dado ilustrativo".

## Ícones

**Lucide** inline em SVG: traço 1,5, pontas arredondadas, 16/20/24 px, cor do texto ou ouro (azul) / Azul Borelli (claro). Nunca emoji na arte, nunca ícone colorido ou 3D, nunca misturar bibliotecas. WhatsApp não existe no Lucide: `message-circle`. Canais oficiais: `shield-check`. Balança e martelo (`scale`, `gavel`) ficam fora. Conjunto curado na seção 11.

## Componentes canônicos

Os nomes de classe são a interface do sistema: **nunca renomeie**. Todos estão na `<style>` do `brand-book.html` e na seção 13.

| Classe | Uso |
|---|---|
| `.sec` + `.sec--noite` / `.sec--papel` · `.sec-head` · `.folio` | seção com fólio e numeral (ouro no azul, Azul Borelli no claro) |
| `.bloco` > `.bloco-head` (`.bloco-n` + `h3` + `.bloco-apoio`) | subseção numerada NN.1, NN.2 |
| `campo-noite` · `campo-mare` · `campo-marinho` · `campo-abismo` · `campo-papel` · `campo-nevoa` · `campo-branco` · `.faixa` | troca de campo num pedaço ou de ponta a ponta |
| `.cols-2` `.cols-3` `.cols-4` `.cols-7-5` `.cols-5-7` `.cols-8-4` `.grade-12` | grades de 12 colunas que empilham no celular |
| `em` no título (o grifo) · `.grifo` · `.rotulo` · `.assinatura` · `.chamada` · `.legenda` | tipografia |
| `.linha` `.linha-v` `.linha--ouro` · `.losango` `.losango--cheio` · `.trama` · `.pilula` · `.selo` | motivos da casa |
| `.btn` + `--cheio` (lê o campo) `--linha` `--avanco` `--baixar` `--bloco` · `.link-seta` | botões, altura mínima 48 |
| `.nota` · `.alerta` · `.aviso-pub` | avisos; aviso de publicidade |
| `.faca` / `.nao-faca` · `.par` · `.nf-grid` > `.nf` | Assim / Não assim · galeria "Não faça" |
| `.cor` · `.leituras` > `.leitura-par` | ficha de cor com contraste calculado |
| `.table-wrap` > `table.consulta` · `.table-wrap.matriz` | tabela que vira cartão no celular · matriz com rolagem local |
| `.kpi-grid` > `.kpi` | número antes do rótulo |
| `.olho` | olho de revista (citação real em Newsreader Italic) |
| `.id-oab` · `.pc-id` | bloco de identificação da OAB |
| `.canais` | selo de canais oficiais |
| `.prancha` · `.foto-sombra` | foto com passe-partout · sombra de leitura |
| `.mock` + formato (post-45, post, post-34, story, reels, whats, celular, doc-pagina, a5, cartao, email, banner, banner-m) > `.peca` | mockups em escala real com `--u`; `.peca--segura` para story e reels |
| `.grafico` > `.grafico-svg[data-bviz]` · `.forma` > `.forma-svg[data-bforms]` | motores |
| `.checklist` > `.check-row` | checklist de aprovação |
| deck: `.slide` + `capa` `capa-clara` `secao` `ideia` `stat` `grafico` `compara` `citacao` `passos` `closer` · `aside.notas` | apresentação |

Espaço só na escala de 4 (4, 8, 12, 16, 24, 32, 48, 64, 96, 128). Respiro lateral 48 px no desktop, 32 até 1024, 20 até 640.

## Aplicações (medidas na arte final)

| Peça | Formato | Regra principal |
|---|---|---|
| Carrossel | 1080 × 1350, margem 72 | capa Noite (trama opcional) com a pergunta e um grifo; miolo Papel com numeral Azul Borelli; lâmina final com chamada educativa, canais oficiais, identificação e aviso |
| Post único | 1080 × 1350 ou 1080 × 1080 | poucas palavras na arte; o resto vai na legenda |
| Story | 1080 × 1920 | 250 px livres no topo e na base; tudo importante nos 1420 do meio |
| Capa de reels | 1080 × 1920 | título e rosto dentro do recorte central da grade |
| Capa de destaque | 1080 × 1080 | ícone Lucide fino em ouro sobre Noite |
| Avatar | símbolo ouro sobre Noite | escritório e atendimento; perfis pessoais usam retrato real |
| Status de WhatsApp | 1080 × 1920 | tipográfico, com o bloco de identificação dentro da peça |
| Papel timbrado, procuração, contrato | A4, branco | marca Azul Borelli; rodapé com a razão social e o registro |
| Proposta de honorários | A4 | capa Noite, miolo branco; valor só na proposta individual para quem pediu |
| Manual do cliente | A4 ou PDF | etapas do caso, canais oficiais, alerta de golpe, glossário |
| Cartão de visita | 90 × 50 mm | assinatura com no mínimo 45 mm; identificação completa |
| Assinatura de e-mail | tabela de 600 px | compatível com Gmail e Outlook (bloco 16 do `lockup.html`) |
| Site e landing page | 12 colunas | topo em Noite ou foto real com sombra; botão "Fale com o escritório"; rodapé com identificação, canais e aviso; imagem de compartilhamento 1200 × 630 |
| Placa e sinalização | por fundo | discreta; letreiro iluminado é zona cinzenta |

Detalhe completo, mockups e textos prontos nas seções 14 a 18.

## Dois formatos de primeira classe

**Documento** (`brand-book.html` é o template): leitura, proposta, relatório, manual. Uma coluna de leitura (máximo 680 px de texto), seções numeradas com fólio, sumário depois da introdução, alternância de campos como numa revista.

**Deck** (`deck-template.html`): reunião, palestra, projeção. Canvas 1440 × 900 escalado; `<section class="slide TIPO">` com os dez tipos acima; setas, espaço, Home/End e toque; barra de progresso; contador; **P** abre as notas; **F** tela cheia; `#3` abre o terceiro slide; no celular os slides empilham.

Vai ser **lido** → documento. Vai ser **apresentado** → deck.

## Mobile System v1 (TRAVADO)

Tudo legível e sem corte entre **320 e 430 px**. Breakpoints 1024 e 640 (e 380 para display). Grades empilham; tabelas de consulta viram cartões pelo script `<script data-borelli-responsive="v1">` do fim do `brand-book.html` (copie literal); matriz larga com rolagem local sinalizada; `overflow-wrap:anywhere` em texto corrido; mídia com `max-width:100%`; botões de 48 px. **PROIBIDO `overflow-x:hidden` no `html` ou no `body`.**

## Exportar PDF

**Pelo Chrome:** abra o HTML, espere 3 segundos, `Cmd+P`, Salvar como PDF, **Gráficos de segundo plano LIGADO** (sem isso o azul some). Documento em retrato com margens padrão; deck em paisagem sem margens.

**Automatizado:** `python3 exportar_pdf.py [arquivo.html]` (Playwright, `print_background=True`, respeita a página do próprio arquivo). **Nunca use `--print-to-pdf` do Chrome.**

## Pendências com a Borelli (não resolva por conta própria)

**Decisões jurídicas (P1 a P4):**
- **P1 · Nome de apresentação:** a razão social obrigatória é "Caico Borelli Sociedade Individual de Advocacia" (Estatuto, art. 16, § 4º; Provimento 170/2016); "Borelli Advocacia" como marca é zona cinzenta até consulta ao TED da OAB/CE. Até lá: o logotipo continua; toda peça traz a razão social no bloco de identificação.
- **P2 · "Advocacia especializada" e "especialista":** exigem título certificado na área (Provimento 205, art. 3º). Sem o certificado, use a versão **reduzida** (sem a linha de apoio) e "atuação em Direito da Saúde".
- **P3 · Chamadas de contato:** gratuidade ("análise sem compromisso") é vedada e convites como "Quero analisar meu caso" ficam na zona cinzenta. Até a decisão, valem as chamadas dos três níveis.
- **P4 · Atendimento por IA:** consentimento escrito do cliente, identificação como máquina e direito de falar com uma pessoa.

**Pendências de informação (1 a 15, mesma numeração da seção 23):**
1. Arquivo original do logotipo e validação das versões reconstruídas.
2. Título que sustenta "especializada" e "especialista" para cada advogado.
3. Registro da sociedade na OAB/CE e OAB completa de cada advogado (conferir no Cadastro Nacional dos Advogados).
4. Endereço oficial que vai nas peças e horário de atendimento.
5. Canais oficiais: WhatsApp definitivo com conta verificada, e-mails, telefone.
6. Unificação dos @ e das páginas nas redes.
7. Nome e marca de unidades em outros estados, se houver.
8. Comunidades: nome, regras e se fica uma ou as duas.
9. Política de avaliações, depoimentos e uso de imagem.
10. Parcerias e indicação em formato compatível com a OAB.
11. Números de experiência em materiais antigos: sair ou virar dado biográfico ("Inscrito na OAB/CE desde [ano]").
12. Sessão de fotos real, para substituir imagens de banco e de IA.
13. Domínio e imagem de compartilhamento do site.
14. Tratamento escrito ("você"), regionalismos e uso de "Dr." nas peças.
15. Inscrição suplementar em outras seccionais quando a peça anunciar atendimento em outros estados.

Também em aberto: CMYK e Pantone (prova de gráfica) e Newsreader e Lexend no Canva e no editor de vídeo.

Quando uma peça esbarrar numa pendência, entregue a versão permitida (dado em `[nº]`, versão reconstruída da marca com o rótulo, sem o termo bloqueado) e diga em uma linha qual pendência trava o resto.

## Checklist de aprovação de peça

- [ ] Marca é arquivo de `assets/`, versão certa para o fundo, com respiro e acima do mínimo (completa 200 px / 560 u; abaixo disso a reduzida ou o símbolo).
- [ ] Só cores da tabela; ouro nunca como texto no claro; um elemento metálico; ouro ≤ 5% da área.
- [ ] Newsreader no título com **um** grifo; Lexend no resto; nenhum texto de peça 1080 abaixo de 26 px.
- [ ] A peça ensina algo; a chamada é do nível certo (educativa no conteúdo; contato como informação; atendimento só para quem já procurou).
- [ ] Nenhuma promessa, superlativo, "especialista", número de processos, êxito, preço, gratuidade, "sem compromisso", caso, decisão ou depoimento.
- [ ] Bloco de identificação dentro da peça quando ela sai do perfil; números em `[nº]` se não confirmados; aviso de publicidade onde couber.
- [ ] Foto real, com autorização, sem luz colorida, sem cliente, sem corpo, sem IA.
- [ ] Norma citada com número e conferida (RN 566/2022, não RN 259).
- [ ] Zero travessão, zero emoji na arte (💙 só em legenda e WhatsApp, no máximo um), no máximo uma exclamação.
- [ ] Contraste AA; texto alternativo em toda imagem.
- [ ] Testado no celular: peça reduzida a 36% ainda se lê; página sem corte de 320 a 430 px.
- [ ] Aprovada pelo advogado responsável.

## Gotchas (vão te morder)

1. **Uma única `<style>` por arquivo.** Print e gráfico entram nela.
2. **A marca é arquivo, não código.** Se você está escrevendo `<path>` de logotipo, BORELLI em fonte ou data URI de memória, pare: use `assets/` ou o `lockup.html`. Nunca cole o SVG do logotipo no HTML (os ids dos degradês colidem): use `<img>`.
3. **Ouro no claro tem 2,3:1.** No claro, a ênfase é Azul Borelli; o grifo é marca-texto `#FFE9A8`.
4. **O grifo não é itálico.** `<em>` no título vira marca-texto ou sublinhado dourado; itálico só em citação e latim.
5. **A completa some abaixo de 200 px.** No rodapé de post, a reduzida ou o símbolo.
6. **Ouro puro sobre Azul Borelli em texto pequeno reprova (4,2:1):** use champanhe.
7. **IDs de SVG únicos** por página (prefixe).
8. **OAB nunca inventada.** `[nº]` até o escritório confirmar.
9. **"Especialista", "referência", "vitória", "sem compromisso"** não entram em copy pública, nem em bio.
10. **`print_background=True`** ou "Gráficos de segundo plano" ligado, senão o azul some.
11. **Caminho relativo sempre** (`assets/...`); para enviar, `python3 autocontido.py`.

## O que o Grifo Nosso NÃO é

- Não é luxo genérico: nada de mármore, brilho, folha de ouro simulada, 3D.
- Não é clichê jurídico: nada de balança, martelo, coluna grega, livro de leis.
- Não é ouro espalhado: é uma linha, um rótulo, um grifo.
- Não é propaganda: não oferece, não promete, não comemora liminar.
- Não é banco de imagem, pessoa gerada por IA, corpo ou antes e depois.
- Não é a marca redesenhada, recolorida ou digitada.
- Não é caixa alta longa, travessão ou emoji na arte.

---

Marca, símbolo e logotipo são propriedade de Caico Borelli Sociedade Individual de Advocacia. Sistema de identidade organizado com a GrowAI. Grifo Nosso v1 · setembro de 2026.
