# Landing Page de Mussarela — 3G Foods

**Documento de handoff para o Lovable**  
**Versão:** 1.0 — 26/08/2026  
**Autor:** Manus AI  
**Objectivo:** construir uma landing page de campanha para mussarela B2B, com arquitectura preparada para evoluir para páginas individuais por produto, marca ou formato.

## 1. Contexto e decisão estratégica

A página deve funcionar como uma **vitrine de soluções de mussarela para negócios de alimentação**, e não como uma página isolada de um único SKU. A campanha actual de Google Ads é **“3G Foods - Queijo Mussarela Atacado (SP + Campinas)”**, campanha de Pesquisa `24169885617`, activa e em aprendizagem com estratégia `TARGET_SPEND`. O histórico disponível é ainda pequeno: a verificação mais recente registou 62 impressões, 9 cliques, 0 conversões e R$ 0,00 de valor atribuído. Portanto, a primeira versão da página deve priorizar clareza, velocidade, confiança, medição e correspondência entre intenção de pesquisa, anúncio e destino; não deve depender de claims agressivos ou de optimizações baseadas numa amostra mínima.

A loja posiciona a 3G Foods como distribuidora food service com mais de 300 produtos, mais de 15.000 clientes activos, mais de 200 municípios atendidos e mais de 1.400 pontos de entrega diários. A operação declara atendimento a restaurantes, supermercados, cozinhas industriais, açougues e distribuidores, com foco em qualidade, pontualidade, frescor, segurança, atendimento personalizado e distribuição eficiente.[1]

> **Direcção de Growth:** o sucesso será medido por pedidos, receita, margem, novos clientes B2B e recompra — não apenas por CTR, CPC ou sessões. A página deve ser construída para permitir o ciclo investimento → clique → comportamento → cadastro/carrinho/checkout → pedido → receita → recompra.

## 2. Objectivo da página

O objectivo primário é encaminhar tráfego qualificado para a compra ou para o próximo passo comercial adequado, conforme o utilizador esteja ou não elegível para comprar online. A página deve oferecer dois caminhos claros: **“Ver mussarelas disponíveis”** para quem quer explorar os produtos e **“Comprar agora”** para quem já está pronto para comprar. O CTA deve levar para a loja, para uma categoria/colecção de mussarela ou para o cadastro/CEP, conforme a URL real disponibilizada na implementação.

O objectivo secundário é capturar procura e intenção para futuras páginas individuais. A estrutura deve permitir que cada card de produto tenha uma URL própria, `slug`, nome, marca, formato, aplicação, disponibilidade, preço e CTA configuráveis sem refazer a página inteira.

| Elemento | Decisão para a V1 |
|---|---|
| Mercado | B2B alimentar no Estado de São Paulo, com prioridade para SP, RMSP e Campinas, conforme campanha actual |
| Público | Pizzarias, restaurantes, lanchonetes, hamburguerias, padarias, mercados, cozinhas profissionais e distribuidores |
| Intenção | Compra/abastecimento de mussarela no atacado e food service |
| Conversão primária | `purchase` atribuído ao tráfego da campanha |
| Microconversões | Clique em produto, clique em comprar, início de cadastro, validação de CEP, início de checkout e clique em WhatsApp/telefone |
| CTA principal | Comprar mussarela no atacado |
| CTA secundário | Ver opções disponíveis |
| Tom | Directo, comercial, confiável, orientado a rendimento operacional e abastecimento |
| Restrição | Não inventar preço, gramagem, marca, rendimento, disponibilidade, certificação ou prazo por produto |

## 3. Arquitectura recomendada

A página deve ser uma única rota de campanha, idealmente `/mussarela-atacado` ou `/mussarela-food-service`, com componentes reutilizáveis para que, no futuro, cada produto possa ocupar uma rota como `/mussarela/bonissimo`, `/mussarela/fatiada` ou `/mussarela/para-pizzaria`. A navegação deve ser curta e não competir com o CTA principal.

### Ordem das secções

1. **Barra de confiança:** “Atendimento B2B | Entrega em regiões atendidas | Compra online e suporte especializado”. Não apresentar como garantia universal; usar apenas o que estiver operacionalmente confirmado.
2. **Hero:** promessa principal, subheadline, CTA primário, CTA secundário, imagem de produto/aplicação sem texto embutido.
3. **Selecção de mussarelas:** cards com filtros simples por aplicação, formato, marca e estado de disponibilidade, quando esses dados existirem.
4. **Bloco por aplicação:** pizzarias, restaurantes/lanchonetes, padarias/mercados e cozinhas profissionais. Cada bloco deve explicar o contexto de uso sem prometer rendimento numérico sem comprovação.
5. **Por que comprar com a 3G Foods:** abastecimento, portfólio, atendimento e distribuição.
6. **Como comprar:** escolher produto, confirmar região/CEP, criar conta ou entrar, finalizar pedido.
7. **Prova de confiança:** números institucionais já exibidos na loja, com fonte e data de revisão interna; não utilizar avaliações inventadas.
8. **FAQ SEO e comercial:** dúvidas sobre atacado, atendimento, regiões, cadastro, compra para CNPJ, entrega e disponibilidade.
9. **CTA final:** “Abasteça seu negócio com mussarela e outros itens food service”.
10. **Rodapé:** links legais, contacto, redes e WhatsApp oficiais já presentes na loja.

## 4. Regras de UX e implementação

A experiência deve ser mobile-first, com o primeiro CTA visível sem scroll em telemóveis comuns. O hero deve utilizar uma composição com área livre para o texto HTML; não colocar headline, preço ou CTA dentro da imagem. O botão primário deve manter contraste AA, ter área de toque confortável e aparecer novamente depois da grelha de produtos e no final da página.

Os cards devem aceitar estados de **disponível**, **sem preço público**, **indisponível temporariamente** e **ver detalhes**. Se o preço depender de login, região, CNPJ, embalagem ou disponibilidade, utilizar a mensagem “Consulte preço e disponibilidade” em vez de preencher um valor fictício. Cada card deve ter `product_id` ou `slug` e evento próprio para permitir destinos individuais no futuro.

A página não deve criar fricção com pop-ups na primeira visita. O WhatsApp deve funcionar como caminho de apoio, não como substituto silencioso da compra online. O link deve usar o número oficial já apresentado pela loja e transportar contexto, por exemplo: “Olá, vim da campanha de mussarela da 3G Foods e quero consultar opções para o meu negócio.”

## 5. Dados que o Lovable deve deixar configuráveis

Criar um objecto de configuração central, sem espalhar estes valores pelo código: `campaignName`, `canonicalUrl`, `primaryCtaUrl`, `categoryUrl`, `signupUrl`, `cepUrl`, `whatsappUrl`, `phone`, `products[]`, `applications[]`, `faq[]`, `trustStats[]`, `lastReviewedAt` e `analyticsMeasurementId`. Os dados de produto devem suportar `name`, `brand`, `format`, `application`, `image`, `priceLabel`, `availability`, `description`, `destinationUrl`, `sku` e `trackingLabel`.

A V1 deve ser publicada apenas depois de confirmar as URLs reais da categoria/colecção de mussarela e dos produtos. Se a loja ainda não tiver uma categoria dedicada, usar temporariamente a rota de pesquisa ou uma rota de campanha rastreável, mas registar essa decisão para substituição posterior.

## 6. Critérios de aceitação

A implementação será considerada pronta quando: o hero comunicar mussarela para negócios em menos de cinco segundos; todos os CTAs conduzirem a destinos reais; a página funcionar em mobile e desktop; os cards aceitarem URLs individuais; não existirem claims não verificados; o carregamento não depender de imagens gigantes; o preço não for inventado; o formulário ou CTA de cadastro não perder parâmetros UTM; os eventos de analytics forem disparados uma única vez; o FAQ tiver marcação estruturada válida; e existir uma checklist de teste antes do tráfego pago.

## 7. Factos, hipóteses e limitações

**Factos confirmados:** a loja apresenta os números institucionais e categorias descritos acima; o catálogo público mostra “QJ Mussarela BONISSIMO” como destaque; a campanha `24169885617` existe e foi reportada como activa, em Pesquisa e em aprendizagem; existe uma acção de compra baseada no evento GA4 `purchase`, activa e incluída na coluna principal de conversões.[1][2]

**Hipóteses de comunicação:** compradores B2B tendem a responder a abastecimento, previsibilidade, aplicação no negócio, disponibilidade, preço/margem e facilidade de reposição. Estas hipóteses devem ser validadas por dados de comportamento, pedidos e margem; não são resultados já comprovados.

**Limitações:** não há no contexto disponível uma ficha técnica completa da mussarela, lista validada de SKUs, gramagens, margens, SLA de entrega por CEP, dados de termos de pesquisa ou histórico suficiente de conversão. O Lovable deve manter estes campos configuráveis e não preencher lacunas com texto inventado.

## Referências

[1]: [Loja 3G Foods — página inicial e posicionamento institucional](https://loja.3gfoods.com.br/)

[2]: [Contexto partilhado — Teste e análise do MCP Google Ads](../Conversa%20%E2%80%94%20Teste%20e%20an%C3%A1lise%20do%20MCP%20Google%20Ads.md)
