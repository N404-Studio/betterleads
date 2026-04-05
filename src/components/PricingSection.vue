<template>
  <section class="pricing" id="pricing">
    <div class="container">
      <div class="pricing__header reveal">
        <span class="pricing__eyebrow">Tarifs</span>
        <h2 class="pricing__h2">Simple et <em>transparent.</em></h2>
        <p class="pricing__intro">
          Pas d'engagement. Pas de frais cachés. Annulez quand vous voulez.
        </p>
      </div>

      <div class="pricing__grid">
        <div
          v-for="(plan, i) in plans"
          :key="plan.name"
          :class="['pricing__card', plan.highlighted ? 'pricing__card--highlight' : '', `reveal reveal-delay-${i + 1}`]"
        >
          <div v-if="plan.badge" class="pricing__badge">{{ plan.badge }}</div>

          <div class="pricing__plan-name">{{ plan.name }}</div>
          <div class="pricing__price">
            <span class="pricing__amount">{{ plan.price }}</span>
            <span class="pricing__period">{{ plan.period }}</span>
          </div>
          <p class="pricing__tagline">{{ plan.tagline }}</p>

          <ul class="pricing__features">
            <li v-for="feat in plan.features" :key="feat" class="pricing__feature">
              <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
              {{ feat }}
            </li>
          </ul>

          <a href="#demo" :class="['btn', plan.highlighted ? 'btn-primary' : 'btn-outline', 'pricing__cta']">
            {{ plan.cta }}
          </a>
        </div>
      </div>

      <p class="pricing__reassurance reveal">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="11" width="18" height="11" rx="2" ry="2"/><path d="M7 11V7a5 5 0 0 1 10 0v4"/></svg>
        Paiement sécurisé · Sans engagement · Remboursé si insatisfait sous 14 jours
      </p>
    </div>
  </section>
</template>

<script setup>
const plans = [
  {
    name: 'Starter',
    price: '39€',
    period: '/ mois',
    tagline: 'Pour tester et démarrer.',
    badge: null,
    highlighted: false,
    cta: 'Commencer',
    features: [
      '1 site client',
      'Formulaire standard (5 questions)',
      'Scoring automatique',
      'Emails hot / warm / cold',
      'Lien Calendly conditionnel',
      'Support par email',
    ],
  },
  {
    name: 'Pro',
    price: '79€',
    period: '/ mois',
    tagline: 'Pour les coachs qui veulent le meilleur.',
    badge: '⭐ Le plus populaire',
    highlighted: true,
    cta: 'Démarrer en Pro',
    features: [
      '3 sites clients',
      'Formulaire personnalisé (questions illimitées)',
      'Scoring avancé avec pénalités',
      'Notifications email instantanées',
      'Couleurs & police personnalisées',
      'Multiselect & logique conditionnelle',
      'Support prioritaire',
    ],
  },
  {
    name: 'Agence',
    price: '149€',
    period: '/ mois',
    tagline: 'Pour les agences qui revendent le service.',
    badge: null,
    highlighted: false,
    cta: 'Nous contacter',
    features: [
      'Sites illimités',
      'Tout le plan Pro',
      'Dashboard admin multi-clients',
      'White-label (votre marque)',
      'API complète',
      'Onboarding dédié',
      'SLA & support téléphonique',
    ],
  },
]
</script>

<style scoped>
.pricing { background: var(--white); }

.pricing__header {
  text-align: center;
  max-width: 520px;
  margin: 0 auto 64px;
}
.pricing__eyebrow {
  display: inline-block;
  font-size: .75rem;
  font-weight: 600;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin-bottom: 14px;
}
.pricing__h2 {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  line-height: 1.15;
  letter-spacing: -.02em;
  color: var(--ink);
  margin-bottom: 12px;
}
.pricing__h2 em { font-style: italic; color: var(--green); }
.pricing__intro { font-size: .9rem; color: var(--ink-muted); }

.pricing__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  align-items: start;
  margin-bottom: 32px;
}

.pricing__card {
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 32px;
  background: var(--cream);
  position: relative;
  transition: transform .2s, box-shadow .2s;
}
.pricing__card:hover { transform: translateY(-3px); box-shadow: var(--shadow-md); }

.pricing__card--highlight {
  background: var(--green);
  border-color: var(--green);
  color: #fff;
  transform: scale(1.03);
  box-shadow: var(--shadow-lg);
}
.pricing__card--highlight:hover { transform: scale(1.03) translateY(-3px); }

.pricing__badge {
  position: absolute;
  top: -14px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--gold);
  color: #fff;
  font-size: .72rem;
  font-weight: 700;
  letter-spacing: .04em;
  padding: 5px 16px;
  border-radius: var(--radius-pill);
  white-space: nowrap;
}

.pricing__plan-name {
  font-family: var(--font-display);
  font-size: 1rem;
  font-weight: 700;
  letter-spacing: .02em;
  text-transform: uppercase;
  margin-bottom: 20px;
  opacity: .7;
}
.pricing__card--highlight .pricing__plan-name { opacity: .8; color: #fff; }

.pricing__price {
  display: flex;
  align-items: baseline;
  gap: 6px;
  margin-bottom: 8px;
}
.pricing__amount {
  font-family: var(--font-display);
  font-size: 3rem;
  font-weight: 700;
  color: var(--ink);
  line-height: 1;
}
.pricing__card--highlight .pricing__amount { color: #fff; }
.pricing__period {
  font-size: .875rem;
  color: var(--ink-muted);
}
.pricing__card--highlight .pricing__period { color: rgba(255,255,255,.6); }

.pricing__tagline {
  font-size: .85rem;
  color: var(--ink-muted);
  margin-bottom: 28px;
  line-height: 1.5;
  border-bottom: 1px solid var(--border);
  padding-bottom: 20px;
}
.pricing__card--highlight .pricing__tagline {
  color: rgba(255,255,255,.7);
  border-color: rgba(255,255,255,.2);
}

.pricing__features { list-style: none; display: flex; flex-direction: column; gap: 10px; margin-bottom: 28px; }
.pricing__feature {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  font-size: .875rem;
  color: var(--ink-soft);
  line-height: 1.4;
}
.pricing__card--highlight .pricing__feature { color: rgba(255,255,255,.85); }
.pricing__feature svg { flex-shrink: 0; margin-top: 2px; }
.pricing__card--highlight .pricing__feature svg { stroke: rgba(255,255,255,.7); }

.pricing__cta { display: flex; justify-content: center; width: 100%; }
.pricing__card--highlight .btn-primary {
  background: #fff;
  color: var(--green);
  box-shadow: 0 2px 12px rgba(0,0,0,.15);
}
.pricing__card--highlight .btn-primary:hover {
  background: #f4faf7;
}

.pricing__reassurance {
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  font-size: .78rem;
  color: var(--ink-muted);
}

@media (max-width: 900px) {
  .pricing__grid { grid-template-columns: 1fr; max-width: 400px; margin: 0 auto 32px; }
  .pricing__card--highlight { transform: none; }
  .pricing__card--highlight:hover { transform: translateY(-3px); }
}
</style>
