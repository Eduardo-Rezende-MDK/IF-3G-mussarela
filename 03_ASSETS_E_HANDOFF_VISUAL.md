# Assets e handoff visual — Landing de Mussarela

**Versão:** 1.0 — 26/08/2026

## Assets entregues

| Ficheiro | Função | Formato | Uso recomendado | Alt sugerido |
|---|---|---|---|---|
| `assets/hero-mussarela-desktop.jpg` (ou `hero-mussarela-food-service.png`) | Hero Desktop (Split-Hero) | JPG/PNG, 16:9 | Desktop; texto HTML sobre a área esquerda livre | “Queijo mussarela em barra fatiada e pizza saindo do forno a lenha” |
| `assets/hero-mussarela-mobile.jpg` | Hero Mobile | JPG, 4:3 | Dispositivos móveis e telas verticais | “Mussarela em barra de 4kg com fatias, mussarela ralada e pizza artesanal” |
| `assets/hero-mussarela-4kg-rendimento.jpg` | Hero Alternativo (Rendimento) | JPG, 16:9 | Variação com foco em rendimento de corte e mussarela ralada | “Queijo mussarela em barra de 4kg e porção ralada com pizza” |
| `assets/logos/logo_horizontal-color.png` | Logotipo Principal | PNG Transparente | Headers/Navbars em fundo claro | “3G Foods Distribuidora Food Service” |
| `assets/logos/logo_horizontal-branco.png` | Logotipo Negativo | PNG Transparente | Headers/Hero em fundo escuro/dark | “3G Foods Distribuidora Food Service” |
| `assets/logos/logo_horizontal-preto.png` | Logotipo Monocromático | PNG Transparente | Rodapés e materiais monocromáticos | “3G Foods Distribuidora Food Service” |
| `assets/logos/logo_pwa.png` / `logo.png` | Ícone / Símbolo 3D | PNG Transparente | Ícone compacto mobile, avatar e PWA | “3G Foods Ícone” |
| `assets/logos/favicon.png` / `.ico` | Favicon | PNG/ICO 1:1 | Aba do navegador e marcadores | “Favicon 3G Foods” |

As imagens de hero foram criadas sem preço embutido e destacam a barra de queijo mussarela amarela de 4kg para food service. A área esquerda da versão desktop foi mantida visualmente mais limpa para receber o headline, a subheadline e os CTAs em HTML. No mobile, use `assets/hero-mussarela-mobile.jpg` que já possui enquadramento centralizado no produto e na pizza.

## Direcção visual

A linguagem visual deve combinar **food service profissional**, apetência e confiança operacional. Usar fundos claros, azul institucional como cor de acção, vermelho apenas para destaque de prioridade e neutros quentes para alimentos. Evitar estética de supermercado de massa, excesso de selos, claims visuais, explosões de preço e imagens com embalagens de marcas que não tenham sido fornecidas pela 3G Foods.

## Assets que ainda dependem de material da equipa

Para completar a grelha de produtos com exactidão, solicitar ou ligar ao catálogo real: fotografia de cada SKU, nome comercial aprovado, marca, formato/gramagem, preço ou regra de preço, disponibilidade, SKU, aplicação autorizada e URL de destino. Não gerar embalagens, rótulos ou logótipos por IA. Se as fotografias oficiais não estiverem disponíveis, usar cards sem imagem de produto ou uma imagem genérica claramente identificada como ambiente, sem simular a embalagem real.

## Prompt-base para futuros assets de produto

“Criar fotografia de produto para uma landing page B2B food service da 3G Foods. Preservar exactamente o produto, embalagem, marca, proporções, rótulo e cores fornecidos na referência. Fundo limpo e neutro, iluminação de estúdio realista, composição 4:3 com espaço suficiente para card, sem texto adicional, sem preço, sem selo, sem logótipo inventado e sem alterar a identidade da embalagem. O resultado deve ser adequado para catálogo digital e não pode sugerir atributos técnicos que não estejam visíveis ou confirmados.”

## Requisitos de optimização

O Lovable deve criar versões responsivas e servir WebP/AVIF quando possível, mantendo PNG/JPG como fallback. O hero deve ser lazy-loaded apenas se não for o LCP; caso seja o elemento principal acima da dobra, usar preload criterioso e dimensões explícitas para evitar CLS. Definir `width`, `height`, `alt`, `loading`, `decoding` e `fetchpriority` de forma apropriada.

## Critérios de aceitação visual

O asset é aprovado para a V1 se o texto HTML permanecer legível sobre a área esquerda, se o produto não for cortado em desktop, se o crop mobile não esconder a pizza ou a mussarela, se não houver texto ou marca inventada e se a imagem for comprimida sem perda visual relevante. Qualquer substituição futura deve preservar o mesmo enquadramento: foco culinário à direita e área segura à esquerda.
