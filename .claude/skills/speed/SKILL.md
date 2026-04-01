---
name: speed
description: Analisa performance do site makewell.com.br via PageSpeed Insights API e orienta correções para scores próximos de 100
disable-model-invocation: true
allowed-tools: Bash, Read, Grep
---

Rodar análise de performance completa do site makewell.com.br:

1. **Mobile**
   `curl "https://www.googleapis.com/pagespeedonline/v5/runPagespeed?url=https://makewell.com.br&strategy=mobile"`

2. **Desktop**
   `curl "https://www.googleapis.com/pagespeedonline/v5/runPagespeed?url=https://makewell.com.br&strategy=desktop"`

3. **Reportar scores com meta de referência**
   - Performance — meta: 95+
   - Accessibility — meta: 100
   - Best Practices — meta: 100
   - SEO — meta: 100

4. **Reportar Core Web Vitals com status**
   - LCP (Largest Contentful Paint) — ideal: < 2.5s
   - CLS (Cumulative Layout Shift) — ideal: < 0.1
   - INP (Interaction to Next Paint) — ideal: < 200ms
   - FCP (First Contentful Paint) — ideal: < 1.8s
   - TTFB (Time to First Byte) — ideal: < 800ms

5. **Para cada oportunidade de melhoria retornada pela API:**
   - Descrever o problema encontrado
   - Identificar o elemento ou arquivo responsável no projeto
   - Sugerir a correção específica no código

6. **Verificar no código-fonte os itens de maior impacto:**
   - Imagem hero tem `fetchpriority="high"` e sem `loading="lazy"`
   - Demais imagens têm `loading="lazy"`, `width`, `height` e estão em `.webp`
   - Nenhum script de terceiros sem `defer` ou `async` no `<head>`
   - Nenhuma fonte externa (Google Fonts, Typekit etc.)
   - CSS crítico inline ou carregado antes de qualquer JS
   - Nenhum recurso desnecessário bloqueando renderização

7. **Ao final, reportar:**
   - Score atual vs meta para cada categoria
   - Lista priorizada de correções para subir o score
   - Itens que já estão no limite do que o hosting permite

Resultado: ✅ atingiu a meta / ⚠️ próximo da meta / ❌ abaixo da meta