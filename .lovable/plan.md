

# Melhorar Botoes e Alinhamento da Landing Page

## Problemas identificados
1. Os botoes "Testar Gratis" (navbar) e "Testar Gratis Agora" (hero) levam direto ao cadastro, sem o usuario ver os precos antes - causa confusao
2. O badge "Sem cartao de credito" e falso e precisa ser removido
3. Os botoes "Comecar Agora" dos planos Inicial e Franquias estao em cinza (`bg-muted`) e sao pouco legiveis

## O que muda

### Botoes da Navbar e Hero
- **Navbar**: "Testar Gratis" vira **"Conheca os Planos"** e faz scroll suave ate a secao de precos (#precos)
- **Hero**: "Testar Gratis Agora" vira **"Conheca os Planos"** e tambem faz scroll ate #precos
- O menu mobile tambem recebe a mesma alteracao

### Trust Badges (Hero)
- Remover "Sem cartao de credito"
- Manter "7 dias gratis" e "Suporte humanizado"

### Botoes dos Planos (PricingSection)
- Trocar `bg-muted hover:bg-muted/80` por um estilo com borda dourada e texto legivel: `border border-gold/50 bg-gold/10 hover:bg-gold/20 text-foreground font-semibold`
- Os 3 planos ficam com botoes visiveis e legíveis

## Detalhes Tecnicos

### `src/components/landing/Navbar.tsx`
- Desktop (linha 86-88): Trocar `Link to="/auth?tab=signup"` por `button onClick scroll to #precos`, texto "Conheca os Planos"
- Mobile (linha 160-165): Mesma alteracao

### `src/components/landing/HeroSection.tsx`
- Botao principal (linhas 58-65): Trocar `navigate("/auth?tab=signup")` por scroll suave ate `#precos`, texto "Conheca os Planos"
- Trust badges (linhas 85-89): Remover o bloco "Sem cartao de credito"

### `src/components/landing/PricingSection.tsx`
- Botao dos planos nao-highlighted (linha ~179): Trocar classes `bg-muted hover:bg-muted/80` por `border border-gold/50 bg-gold/10 hover:bg-gold/20 text-foreground font-semibold`

