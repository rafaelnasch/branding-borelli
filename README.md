# branding-borelli

**A identidade visual da Borelli Advocacia, empacotada como uma Skill do Claude.** Sistema Grifo Nosso v1.

Instale uma vez e peça o material em português. O Claude passa a produzir post, carrossel, story, reels, WhatsApp, site, landing page, proposta de honorários, contrato, manual do cliente, apresentação, e-mail e impresso **já no padrão da Borelli**: cor certa, fonte certa, marca certa, tom certo e as regras de publicidade da advocacia da OAB, sem você precisar explicar nada disso de novo.

> "Faz um carrossel de 6 lâminas da Borelli sobre a negativa por escrito."
> "Monta um story no padrão da Borelli com os canais oficiais e o alerta de golpe."
> "Cria uma apresentação de 8 slides da Borelli para uma palestra sobre plano de saúde."

**Ver o brand book no navegador:** [rafaelnasch.github.io/branding-borelli](https://rafaelnasch.github.io/branding-borelli/) (abre em qualquer aparelho, sem instalar nada).

---

## O que vem na caixa

| Arquivo | O que é |
|---|---|
| `SKILL.md` | O estilo inteiro, travado: cores, tipografia e o grifo, a marca, as cinco leis, voz, publicidade da advocacia, medidas de cada peça, celular e PDF. É o que o Claude lê. |
| `brand-book.html` | **Abra primeiro.** O manual vivo em 24 seções, com modelos de peça em tamanho real, e o template pronto de **documento**. |
| `deck-template.html` | O esqueleto de **apresentação**: dez tipos de slide em 1440 × 900, navegação por seta, notas na tecla **P**. |
| `lockup.html` | Os snippets prontos: marca em arquivo e em data URI, símbolo e avatar, favicon, bloco de identificação da OAB, selo de canais oficiais, aviso de publicidade, o grifo, a linha e o losango, respiro e assinatura de e-mail. |
| `bviz.js` | Motor de gráficos em SVG puro: barras, ranking, linha, composição, anel, funil, fluxo, número em destaque, linha do tempo e cota. |
| `bforms.js` | Motor de formas da casa, tiradas da geometria do símbolo: linha, losango, elo, avanço, percurso, trama, grade de 45°, moldura e grifo. |
| `dist/` | **Para enviar a alguém.** Versões de arquivo único (imagens, fontes e motores embutidos): `brand-book-borelli.html`, `apresentacao-borelli.html` e `assinaturas-borelli.html`. Abrem sozinhas no e-mail, WhatsApp, Drive e celular. |
| `autocontido.py` | Gera o `dist/` de novo: `python3 autocontido.py`. Também transforma qualquer HTML novo feito com a skill: `python3 autocontido.py meu-material.html`. |
| `exportar_pdf.py` | Exporta documento ou apresentação em PDF com o Playwright. |
| `assets/` | A marca em SVG e PNG (horizontal, reduzida, vertical, símbolo, avatar e favicon, em ouro, Azul Borelli, Azul Noite, branco e ouro chapado), os desenhos de construção do símbolo (`formas/`), as fotos reais (`fotos/`), as fontes (`fontes/`) e os arquivos publicados que serviram de base (`referencia-original/`). |

## Instalar

O nome da pasta tem que ser exatamente `branding-borelli`, com o `SKILL.md` dentro.

### Claude Code (terminal, VS Code, app de desktop)

```bash
git clone https://github.com/rafaelnasch/branding-borelli.git ~/.claude/skills/branding-borelli
```

Abra uma sessão nova e digite `/branding-borelli`, ou simplesmente peça "faz no padrão da Borelli". Para atualizar:

```bash
cd ~/.claude/skills/branding-borelli && git pull
```

### Claude no navegador ou no celular (claude.ai)

1. Baixe o ZIP pronto na página de **[Releases](https://github.com/rafaelnasch/branding-borelli/releases/latest)**: o arquivo `branding-borelli.zip`.
2. No Claude, vá em **Settings, Capabilities, Skills** e envie o ZIP.

> Use o ZIP do Releases, **não** o "Code, Download ZIP" do GitHub: aquele vem com o nome da pasta trocado (`branding-borelli-main`) e a skill sobe com o nome errado.

No navegador o material sai como arquivo único, com a marca e os gráficos embutidos. A skill já sabe fazer isso. Só o PDF muda: ela entrega o HTML e você imprime pelo Chrome (instruções abaixo).

### Codex CLI

```bash
git clone https://github.com/rafaelnasch/branding-borelli.git ~/.codex/skills/branding-borelli
```

## O primeiro teste

Abra uma conversa nova e peça:

> "Faz um post 1080 × 1350 no padrão da Borelli sobre a negativa por escrito."

Se vier campo Azul Noite (ou Papel), título em serifa com **uma** palavra grifada (sublinhado dourado no azul, marca-texto no claro), a marca em ouro só sobre o azul, uma chamada educativa ("Salve para consultar depois") e nenhuma oferta nem promessa, está funcionando. Se vier um post genérico, a skill não carregou: feche e abra o Claude de novo e confira se a pasta se chama exatamente `branding-borelli` e tem o `SKILL.md` dentro.

## Usar

- **"faz no padrão da Borelli"** já aciona a skill;
- diga **qual peça** (carrossel, post, story, reels, status de WhatsApp, página, proposta, contrato, manual do cliente, apresentação, e-mail, cartão) e **o tema**: a skill já sabe a medida de cada formato;
- diga se é para **ler** (documento) ou para **apresentar** (deck);
- o registro da sociedade na OAB e os dados ainda não confirmados saem como `[nº]`: preencha antes de publicar;
- toda peça passa pelo advogado responsável antes de ir ao ar;
- para **PDF**: abra o HTML no Chrome, espere uns 3 segundos, `Cmd+P`, **Salvar como PDF** e, em "Mais configurações", ligue **Gráficos de segundo plano**. Sem isso o fundo azul some. Apresentação: layout **Paisagem**, margens **Nenhuma**.

## As cinco leis da casa

1. **O dourado é da marca.** O metal vive no logotipo. Fora dele, o ouro é linha fina, rótulo e numeral sobre o azul. No claro, nunca é texto. No máximo 5% da área.
2. **Um grifo por título.** Uma palavra recebe o grifo: é a parte que decide. Se falta espaço, corta-se texto, nunca margem.
3. **Informar, nunca oferecer.** Toda peça ensina algo. Nenhuma oferece serviço ou convida a processar. O contato aparece como informação, nos canais oficiais.
4. **Gente de verdade, com autorização.** Só fotos reais do escritório e da equipe. Nada de banco de imagem, pessoa gerada por IA ou cliente.
5. **Nenhuma promessa, nenhuma comparação.** Sem resultado prometido ou comemorado, sem superlativo, sem número de processos, sem preço ou gratuidade. Nome e OAB sempre que a regra pedir.

## A marca

O logotipo da Borelli **nunca** é redesenhado, redigitado, recolorido fora das versões ou vetorizado por conta própria. É sempre um dos arquivos de `assets/`. Fundo azul pede a versão em ouro metálico; fundo claro pede a Azul Borelli; foto escura pede a branca; bordado, carimbo e gravação pedem o ouro chapado. Abaixo de 200 px de largura entra a assinatura reduzida (sem a linha "Advocacia Especializada"); abaixo de 100 px, só o símbolo. Os arquivos são uma **reconstrução vetorial** feita a partir dos arquivos publicados pelo escritório e serão trocados, com o mesmo nome, quando o arquivo original do designer chegar.

## Publicidade da advocacia

O manual segue o Provimento 205/2021 do Conselho Federal da OAB, o Código de Ética e Disciplina e o Estatuto da Advocacia, sempre na leitura mais cuidadosa. Ele não substitui a análise ética do escritório nem uma consulta ao Tribunal de Ética e Disciplina da OAB/CE. Detalhe, fontes e modelos na seção 08 do brand book.

## Pendências com a Borelli

Até cada uma ser resolvida, a skill entrega só a versão permitida. A lista completa, com o que fica travado e o que fazer enquanto isso, está na seção 23 do brand book e no `SKILL.md`.

## Navegador

Chrome, Edge ou Safari recentes (iOS 16 ou mais novo, Chrome 105 ou mais novo).

---

Marca, símbolo e logotipo são propriedade de **Caico Borelli Sociedade Individual de Advocacia**. Os motores `bviz.js` e `bforms.js` foram escritos para este sistema. Sistema de identidade organizado com a GrowAI. Grifo Nosso v1 · setembro de 2026.
