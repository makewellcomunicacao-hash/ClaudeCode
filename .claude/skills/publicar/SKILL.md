---
name: publicar
description: Verifica SEO, roda análise de performance, atualiza sitemap.xml e publica o site no GitHub Pages
disable-model-invocation: true
allowed-tools: Bash, Edit, Read, Glob
---

Publicar o site makewell.com.br no GitHub Pages:

PRÉ-PUBLICAÇÃO:

1. Rodar `/revisar` e confirmar que não há itens ❌ antes de continuar
2. Rodar `/seo` e confirmar que não há itens ❌ antes de continuar
3. Rodar `/speed` e registrar os scores atuais para comparar após o deploy

PUBLICAÇÃO:

4. Verificar o status atual: `git status`
5. Abrir `sitemap.xml` e atualizar TODOS os `<lastmod>` com a data
   de hoje (formato YYYY-MM-DD)
6. Fazer `git add .`
7. Fazer commit com mensagem descritiva em português
8. Fazer `git push origin main`
9. Confirmar ao usuário que o deploy foi iniciado — GitHub Pages leva
   1-3 minutos para publicar

PÓS-PUBLICAÇÃO:

10. Aguardar 3 minutos e rodar `/speed` novamente
11. Comparar scores antes e depois do deploy e reportar diferenças

Regras obrigatórias:
- NUNCA fazer push com itens ❌ pendentes no /revisar ou /seo
- NUNCA fazer push sem atualizar o sitemap primeiro
- Mensagens de commit sempre em português
- Incluir o sitemap no mesmo commit das alterações