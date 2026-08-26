# Prompt para o Lovable — Landing Page de Mussarela 3G Foods

Construa uma landing page responsiva, mobile-first e orientada a conversão para a campanha B2B de mussarela da 3G Foods. A página é uma vitrine de várias opções de produto, mas deve nascer com arquitectura preparada para destinos individuais futuros por SKU, marca, formato e aplicação.

## Objectivo de negócio

Gerar tráfego qualificado e conduzir compradores B2B para compra online, validação de CEP, cadastro ou atendimento. O público inclui pizzarias, restaurantes, lanchonetes, hamburguerias, padarias, mercados, cozinhas profissionais e distribuidores no Estado de São Paulo, com atenção à área actualmente trabalhada pela campanha: SP, RMSP e Campinas.

## Estrutura obrigatória

Crie as secções nesta ordem: barra de confiança; hero; grelha de mussarelas; aplicações por tipo de negócio; razões para comprar com a 3G Foods; como comprar; prova institucional; FAQ; CTA final; rodapé. Use o seguinte conteúdo-base no hero:

- Eyebrow: “Mussarela para food service”
- H1: “Mussarela para manter o seu negócio sempre abastecido”
- Subheadline: “Encontre opções para pizzarias, restaurantes, lanchonetes, padarias, mercados e cozinhas profissionais. Compre online ou fale com a equipa da 3G Foods para consultar disponibilidade e atendimento na sua região.”
- CTA primário: “Ver mussarelas disponíveis”
- CTA secundário: “Comprar agora”
- Microcopy: “Atendimento para empresas | Consulte regiões e condições de entrega”

Use os assets responsivos no hero: `assets/hero-mussarela-desktop.jpg` (ou `assets/hero-mussarela-food-service.png`) para desktop (com foco à direita e área esquerda livre para HTML) e `assets/hero-mussarela-mobile.jpg` para dispositivos móveis. Para a identidade visual, utilize os logotipos transparentes oficiais em `assets/logos/` (`logo_horizontal-color.png` para fundo claro, `logo_horizontal-branco.png` para fundo dark e `favicon.png` para favicon).

## Produtos e dados

Implemente `products[]` como configuração central com os campos `product_id`, `slug`, `name`, `brand`, `format`, `application`, `image`, `priceLabel`, `availability`, `description`, `destinationUrl` e `trackingLabel`. Não invente preço, gramagem, rendimento, stock, prazo, marca, certificação ou superioridade técnica. Se um dado não estiver confirmado, mostre “Consulte preço e disponibilidade”. O produto público “QJ Mussarela BONISSIMO” só deve ser exibido se a equipa confirmar disponibilidade e URL.

Cada card deve ter CTA e destino configurável. Prepare rotas futuras como `/mussarela/:slug`, mesmo que na primeira versão todos os cards apontem para a categoria ou para um destino temporário validado.

## Dados institucionais permitidos

A loja apresenta mais de 300 produtos, mais de 15.000 clientes activos, mais de 200 municípios atendidos, mais de 1.400 pontos de entrega diários, mais de 10 anos de operação, 6 mil m² de espaço logístico e 2 mil toneladas distribuídas por mês. Use estes números apenas como prova institucional, com nota interna de revisão e sem transformar números operacionais em garantia individual de prazo ou disponibilidade.

## Design e UX

Adopte uma linguagem B2B food service: limpa, profissional, apetecível e confiável. Use azul institucional para acções, vermelho com moderação para prioridade e fundos neutros. Não usar pop-up na primeira visita. Repetir o CTA no fim da grelha e no final da página. Garantir contraste AA, foco visível, teclado, labels, alt text, estados de carregamento, mensagens de erro e áreas de toque confortáveis.

Não criar embalagens, logótipos, selos ou fotos de produto inventadas. Não colocar texto dentro das imagens. Não usar claims “maior rendimento”, “derrete melhor”, “maior margem”, “melhor preço” ou equivalentes sem ficha técnica/prova aprovada.

## SEO

Usar URL canónica `/mussarela-atacado` ou `/mussarela-food-service`, escolhendo apenas uma. Title: “Mussarela no Atacado para Food Service | 3G Foods”. Meta description: “Encontre mussarela para pizzarias, restaurantes, lanchonetes, padarias e outros negócios. Consulte opções, disponibilidade e compre com a 3G Foods.” Usar um único H1, H2s descritivos e conteúdo visível para FAQ. Implementar `ItemList` para a grelha, `Product` apenas para produtos reais e `FAQPage` apenas para perguntas visíveis. Preservar UTMs e não indexar uma rota temporária até que o destino de compra seja funcional.

## Analytics e tracking

Preparar integração com GA4 Measurement ID `G-7CQV85CBHN` e contentor GTM de referência `6326754017 / 236735917`, sem criar nova propriedade. Disparar: `view_landing_mussarela`, `view_item_list`, `select_product`, `select_cta`, `view_item`, `begin_signup`, `cep_check_start`, `whatsapp_click`, `begin_checkout` e `purchase`. Enviar apenas dados não pessoais. Para `purchase`, exigir `transaction_id`, `value`, `currency` e `items`, com deduplicação. Registar `campaign_name`, `page_variant`, localização do CTA e `product_id` quando aplicável.

## Campanha e testes

A campanha de referência é `24169885617 — 3G Foods - Queijo Mussarela Atacado (SP + Campinas)`, Search, estratégia `TARGET_SPEND`, observada em aprendizagem. Não altere campanha, orçamento, anúncios, palavras-chave ou tracking automaticamente. A primeira fase deve validar a página e o funil. Depois, testar uma hipótese por vez: promessa de abastecimento versus catálogo; aplicações antes da grelha versus grelha directa; “Comprar agora” versus “Ver opções”; prova institucional perto do CTA versus no final. Julgar por `begin_checkout`, `purchase`, receita, margem e qualidade do cliente, nunca apenas por CTR ou CPC.

## Entrega

Entregar componentes reutilizáveis, configuração central de conteúdo, rotas preparadas, imagens optimizadas, metadata, schema, eventos documentados e uma checklist de QA. Validar todos os CTAs, UTMs, WhatsApp, cadastro, CEP, login, carrinho, checkout e compra de teste antes de enviar tráfego pago.
