# CML Moodle Widgets (Iframe Micro-Apps)

Micro-widgets interativos em iframe para integração nas páginas de aula do Moodle da Câmara Municipal de Lisboa.

## Finalidade
Permitir a recolha de estatísticas em tempo real (Sondagens e Quizzes) no backend Supabase (`afjxpcooemugajghvhlr`), contornando em absoluto:
1. O bloqueio `403 Forbidden` / Turnstile do Cloudflare WAF da CML para tags `<script>` inline.
2. A sanitização HTML (`clean_text` / KSES) do Moodle.

## Componentes Disponíveis
- **Sondagens (`poll.html`)**: Exibe as opções de votação, grava no Supabase anónimo com fingerprint e anima as barras de percentagem em tempo real.
  - Exemplo: `https://heldertoucas.github.io/cml-moodle-widgets/poll.html?id=poll_1_1`
- **Quizzes (`quiz.html`)**: Validação imediata da resposta, destaque a verde/vermelho, justificação pedagógica detalhada e telemetria de acertos no Supabase.
  - Exemplo: `https://heldertoucas.github.io/cml-moodle-widgets/quiz.html?id=1.1`

## Integração no Moodle
```html
<iframe src="https://heldertoucas.github.io/cml-moodle-widgets/poll.html?id=poll_1_1" 
        style="width: 100%; height: 260px; border: none; border-radius: 12px; overflow: hidden;" 
        loading="lazy"></iframe>
```
