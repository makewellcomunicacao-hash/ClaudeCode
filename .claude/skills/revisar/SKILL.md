---
name: revisar
description: Review completo do index.html — rastreamento, CTA, design, performance e responsividade
disable-model-invocation: true
allowed-tools: Read, Grep
---

Fazer review completo do `index.html` do site makewell.com.br:

1. **Rastreamento**
   - GTM (GTM-NFGD8X8): script no `<head>` e noscript após `<body>`
   - Meta Pixel (ID 2571294026447618): `fbq('init')` e `fbq('track','PageView')` presentes
   - Botões CTA: todos têm `onclick="fbq('track','Lead',{...})"` — verificar se nenhum ficou sem evento

2. **Links e navegação**
   - Links internos (âncoras) apontam para seções existentes
   - Nenhum ID duplicado no HTML
   - Links externos têm `target="_blank" rel="noopener noreferrer"`
   - WhatsApp usa `https://wa.me/5582999103246`

3. **Performance**
   - Imagens em `.webp` com `loading="lazy"` (exceto imagem hero)
   - Imagem hero tem `loading="eager"` ou sem atributo lazy
   - Nenhum `console.log` presente no código
   - Nenhum CSS ou bloco de código duplicado
   - `body::after` grain: sem `mix-blend-mode`
   - Nav scrolled e hero-card: sem `backdrop-filter`

4. **Acessibilidade**
   - Todas as imagens têm atributo `alt` descritivo
   - Botões e links têm texto legível (sem ícone isolado sem label)
   - Contraste adequado entre texto e fundo

5. **Design e padrões visuais**
   - Ler as variáveis de cor definidas no `:root` do CSS do projeto
   - Verificar se há cores hardcoded no HTML/CSS fora das variáveis (ex: #fff inline)
   - Fontes: sem referências a Google Fonts ou fontes externas (apenas system fonts)
   - Nenhum `!important` desnecessário

6. **Mobile e Responsividade**
   - Ler o CSS do projeto para identificar os breakpoints utilizados
   - Verificar se o header fixo tem altura definida e se o conteúdo principal
     tem `padding-top` correspondente
   - Verificar se todos os IDs de âncora têm `scroll-margin-top` igual
     à altura do header lida no CSS
   - Verificar se o hero h1 usa `clamp()` ou valor responsivo conforme
     definido no CSS do projeto
   - Verificar se o menu mobile tem `padding-top` suficiente para não
     sobrepor o header — comparar com a altura real do header no CSS
   - Nenhum elemento com largura fixa em px que estoure o layout em telas < 390px
   - Todas as imagens têm `max-width: 100%`, `height: auto`, `width` e `height` definidos
   - Nenhum `overflow-x` indesejado no body e seções principais
   - Botões e links CTA com área de toque mínima de 44x44px
   - Grids e cards colapsam para coluna única em mobile
   - Nenhum `position: absolute` sobrepondo conteúdo em telas pequenas
   - Padding lateral das seções mínimo de 16px de cada lado em mobile
   - Nenhum texto com fonte menor que 14px em elementos visíveis

7. **Informações da empresa**
   - Endereço: R. Prof. Lourenço Peixoto, 36, Sala 04, Jatiúca, Maceió, AL.
   - CNPJ: 27.238.877/0001-71
   - WhatsApp: +55 82 99910-3246
   - E-mail: contato@makewell.com.br

Reportar resultado em checklist: ✅ OK / ⚠️ Atenção / ❌ Problema