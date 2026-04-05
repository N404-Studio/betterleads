# BetterLeads — Landing Page

Landing page Vue 3 + Vite pour présenter le service BetterLeads aux coachs.

## Démarrer

```bash
npm install
npm run dev
```

## Build production

```bash
npm run build
# Output dans /dist — déployable sur Vercel, Netlify, etc.
```

## Sections

| Section | Composant | Description |
|---------|-----------|-------------|
| Nav | `NavBar.vue` | Navigation fixe avec scroll effect |
| Hero | `HeroSection.vue` | Accroche + mockup widget animé |
| Avant/Après | `BeforeAfter.vue` | Problème vs solution + stats |
| Features | `FeaturesSection.vue` | 6 fonctionnalités clés |
| Comment ça marche | `HowItWorks.vue` | 3 étapes + extrait de code |
| Témoignages | `TestimonialsSection.vue` | 6 avis clients |
| Pricing | `PricingSection.vue` | 3 plans tarifaires |
| CTA + Footer | `CtaFooter.vue` | Appel à l'action final + footer |

## Personnalisation

Couleurs dans `src/assets/global.css` → variables CSS `:root`.

Pour changer l'email de contact CTA : `CtaFooter.vue` → `href="mailto:..."`.
