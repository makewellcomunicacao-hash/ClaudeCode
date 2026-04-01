---
name: seo
description: Auditoria SEO do site makewell.com.br — meta tags, estrutura semântica, Schema.org, sitemap e robots.txt
disable-model-invocation: true
allowed-tools: Read, Grep
---

Fazer auditoria SEO completa do site makewell.com.br:

1. **Meta tags**
   - `<html lang="pt-BR">` presente
   - `<title>` presente, único, até 60 caracteres e contém keyword principal
   - `<meta name="description">` entre 120-160 caracteres
   - `<meta name="robots" content="index, follow">`
   - `<link rel="canonical" href="https://makewell.com.br/">`
   - Open Graph: `og:title`, `og:description`, `og:image`, `og:url`, `og:type` presentes

2. **Estrutura semântica**
   - `<html lang="pt-BR">` presente
   - Existe exatamente 1 `<h1>` na página
   - Hierarquia de headings respeitada: h1 → h2 → h3 sem pular níveis
   - `<h1>` e `<title>` contêm a keyword principal do negócio
     (ex: "agência de marketing", "marketing digital Maceió")
   - Todas as imagens têm atributo `alt` descritivo

3. **Schema.org JSON-LD**
   - Bloco JSON-LD presente no `<head>`
   - `@type`: LocalBusiness com `additionalType: MarketingAgency`
   - Campos obrigatórios: `name`, `url`, `telephone`, `email`, `foundingDate`
   - Campo `address` com `streetAddress`, `addressLocality`, `addressRegion`, `addressCountry`
   - Campo `areaServed` presente (ex: Brasil)
   - Campo `sameAs` com links das redes sociais da empresa

4. **Sitemap**
   - `sitemap.xml` existe e está acessível
   - Todas as páginas do site estão listadas
   - `<lastmod>` atualizado com data recente
   - `<priority>` e `<changefreq>` coerentes para cada URL

5. **Robots.txt**
   - Arquivo `robots.txt` existe
   - Não está bloqueando indexação de páginas importantes
   - Contém `Sitemap: https://makewell.com.br/sitemap.xml`

6. **Core Web Vitals — verificação estática**
   - Todas as imagens têm atributos `width` e `height` definidos (evita CLS)
   - Nenhum recurso crítico bloqueando renderização no `<head>`
   - CSS crítico inline ou carregado antes do JS

Reportar resultado em checklist: ✅ OK / ⚠️ Atenção / ❌ Problema