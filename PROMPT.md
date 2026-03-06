# CTO for a Day — Prompts

## 1. Game (Claude Code)

Crie um jogo web single-file (HTML/CSS/JS) chamado "CTO for a Day".

### Mecânica
- 10 rounds de dilemas de liderança tech
- Cada dilema tem 2 opções e um timer visual de 5 segundos
- Se o timer zerar sem resposta, o sistema decide por você (sempre a pior opção)
- No final: score + veredito personalizado estilo board meeting

### As 20 perguntas (sorteia 10 por jogo)

1. Dev sênior pediu aumento de 40% ou sai na sexta. → Paga | Deixa ir
2. Deploy na véspera do feriado. QA aprovou mas você tem um mau pressentimento. → Sobe | Segura
3. Reescrever o core em microserviços agora ou aguentar o monolito mais 2 anos. → Reescreve | Aguenta
4. Novo dev quer usar Rust em produção. É muito bom tecnicamente. → Deixa | Bloqueia
5. M&A em andamento. Acquirer pediu acesso ao repositório hoje, sem aviso. → Dá acesso | Consulta jurídico
6. Incidente em produção às 23h. Time está exausto. Rollback seguro ou hotfix arriscado? → Rollback | Hotfix
7. PM quer lançar feature com 3 bugs conhecidos de baixa severidade. Prazo apertado. → Lança | Segura
8. Tech lead pediu 2 semanas de refactor sem entrega de feature. → Aprova | Nega
9. Dev júnior commitou direto na main e quebrou o build. É a segunda vez. → Demite | Conversa
10. Você tem budget pra contratar 1 pessoa: dev sênior caro ou 2 plenos medianos. → 1 Sênior | 2 Plenos
11. Stakeholder quer dashboard em PowerPoint antes da demo amanhã. → Faz | Recusa
12. Time quer adotar AI coding assistants. Segurança ainda não aprovou. → Libera | Espera aprovação
13. CTO da empresa adquirente quer usar sua stack como referência. Você sabe que ela tem problemas sérios. → Concorda | Conta a verdade
14. Dev remoto some por 3 dias sem responder. Entrega crítica na semana. → Demite agora | Espera mais 2 dias
15. Dois devs seniores em conflito aberto no Slack. Equipe tomando partido. → Separa os dois | Deixa rolar
16. Você descobriu que um sistema legado crítico não tem backup há 6 meses. → Para tudo e corrige | Agenda pra próxima sprint
17. PM pediu estimativa. Dev disse 2 semanas. Você sabe que é 6. O que você fala pro board? → 2 semanas | 6 semanas
18. Fornecedor de infra anunciou aumento de 60% no contrato. → Migra agora | Negocia e fica
19. Dev quer trabalhar 100% em OSS por 1 mês como "aprendizado". → Deixa | Nega
20. Você tem certeza que a arquitetura atual não aguenta o crescimento projetado. Ninguém mais vê o problema. → Grita o alarme | Resolve sozinho em silêncio

### Vereditos finais por score
- 0-3 acertos: "Você destruiu a empresa em tempo recorde. Conselho agradece a transparência."
- 4-6 acertos: "Sobreviveu. O monolito também. Por enquanto."
- 7-9 acertos: "Eficiente, frio, funcional. Exatamente o que o board queria."
- 10: "Impossível. Você trapaceou ou nunca trabalhou em startup."

### Design — estética "war room"
- Tema escuro, pesado, quase opressivo. Cor dominante: preto grafite #0D0D0D
- Acento vermelho sangue #C0392B para o timer e decisões críticas
- Acento verde terminal #00FF41 para confirmações e score
- Fonte display: algo monospace ou condensed bold — clima de terminal corporativo
- Timer: barra horizontal que drena da direita pra esquerda com animação tensa
- Quando o tempo zera: tela pisca vermelho + som de erro (Web Audio API, simples)
- Transição entre perguntas: corte seco, sem fade suave — decisões não têm gentileza
- Veredito final: aparece como se fosse um memo corporativo sendo digitado na tela
- Layout centralizado, pergunta grande, botões grandes — mobile-friendly
- Nenhum emoji, nenhum gradiente pastel, zero UI kit genérico

---

## 2. Logo/Favicon (Gemini Imagen ou similar)

Create a favicon/logo for a game called "CTO for a Day".

Concept: a cracked coffee mug with a tiny fire inside it. Simple, iconic, slightly dark humor.

Style:
- Flat design, no gradients
- Black background #0D0D0D
- Red #C0392B for the fire and cracks
- White or light gray #E0E0E0 for the mug outline
- Must read clearly at 32x32 and 64x64
- SVG format preferred

No text. No shadows. No glow effects. Pure iconography.

---

## 3. Assets & Meta Integration (Claude Code)

The game already has a logo (logo.png) and a favicon (favicon.png) in the project root.
Integrate both into the existing index.html and enhance the overall presentation:

### Favicon
- Link favicon.png as the browser tab icon
- Also add apple-touch-icon for iOS

### Open Graph / Social Meta Tags
Add full meta tags in the <head> for rich link previews:
- og:title → "CTO for a Day"
- og:description → "10 decisions. 5 seconds each. Think you can run a tech company?"
- og:image → logo.png
- og:type → website
- Twitter Card tags (summary_large_image)

### Logo on start screen
- Display logo.png prominently on the game's intro/start screen
- Keep the war room aesthetic — don't soften the design around it
- Logo should feel like a stamp, not a decoration

### Page title and browser tab
- `<title>` → "CTO for a Day"

### Bonus if it fits the aesthetic
- Add a subtle scanline or noise texture overlay to the background (CSS only, no extra files)
- On the final verdict screen, add a "Share your result" button that copies a pre-formatted text to clipboard:
  "I survived (or didn't) as CTO for a Day. Score: X/10 — [veredito]. Try it: [URL]"
- Add a small "Made with ☕ and bad decisions" footer in monospace, low opacity