# CTO for a Day

> 10 decisões. 5 segundos cada. Você consegue sobreviver como CTO?

![Logo](logo.png)

---

## O que é

Um jogo de navegador de sessão única onde você assume o papel de CTO e precisa tomar decisões difíceis de liderança técnica — sem contexto suficiente, sem tempo pra pensar, exatamente como na vida real.

A cada rodada aparece um dilema. Você tem 5 segundos. Se o timer zerar, o sistema decide por você. E sempre escolhe errado.

No final, o board te julga.

---

## Como surgiu

Nasceu numa conversa de 20 minutos tentando achar um projeto rápido e original pra fazer numa tarde.

A ideia central veio de uma frustração real: decisões de liderança técnica raramente têm resposta certa, mas sempre têm consequências. O humor do jogo está exatamente aí — o sistema julga suas escolhas com a arbitrariedade de um board que nunca escreveu uma linha de código.

A mecânica do timer veio do reconhecimento de que CTOs reais tomam decisões críticas com informação incompleta e pressão de tempo. Simular isso em 5 segundos por decisão captura algo verdadeiro sobre o papel.

---

## Stack

- HTML + CSS + JavaScript puro — single file, zero dependências
- Web Audio API para feedback sonoro
- Sem framework, sem build step, sem backend

---

## Design

Estética **"war room"** — deliberadamente opressiva.

| Elemento | Escolha |
|---|---|
| Background | Preto grafite `#0D0D0D` |
| Acento crítico | Vermelho sangue `#C0392B` |
| Acento positivo | Verde terminal `#00FF41` |
| Tipografia | Monospace condensed — clima de terminal corporativo |
| Transições | Corte seco — decisões não têm gentileza |
| Timer | Barra horizontal que drena da direita pra esquerda |

---

## Como o jogo funciona

1. Tela de abertura com logo e botão de início
2. 10 dilemas sorteados aleatoriamente de um banco de 20 perguntas
3. Cada dilema: pergunta + 2 opções + timer de 5 segundos
4. Timer zerado = sistema decide (sempre a pior opção)
5. Tela de veredito final com score e julgamento do board
6. Botão de compartilhamento copia resultado formatado pro clipboard

---

## Vereditos

| Score | Veredito |
|---|---|
| 0–3 | "Você destruiu a empresa em tempo recorde. Conselho agradece a transparência." |
| 4–6 | "Sobreviveu. O monolito também. Por enquanto." |
| 7–9 | "Eficiente, frio, funcional. Exatamente o que o board queria." |
| 10 | "Impossível. Você trapaceou ou nunca trabalhou em startup." |

---

## Assets

- **Logo e favicon** gerados com Gemini Imagen — caneca rachada com fogo, flat design, sem gradientes
- Watermark removida via script Python (Pillow)
- Meta tags Open Graph e Twitter Card configuradas para preview rico no compartilhamento de links

---

## Como rodar

Sem instalação. Abre o `index.html` no navegador.

Para servir localmente:

```bash
npx serve .
# ou
python3 -m http.server 8080
```

---

## Processo de criação

O projeto foi construído inteiramente com auxílio de IA:

- **Concepção e prompts** — Claude (claude.ai)
- **Código do jogo** — Claude Code
- **Logo e favicon** — Gemini Imagen
- **Tempo total** — menos de 1 hora

Um experimento sobre o que é possível construir com ferramentas de IA atuais quando você sabe o que quer.

---

*Made with ☕ and bad decisions.*