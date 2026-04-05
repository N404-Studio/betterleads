<template>
  <section class="features" id="features">
    <div class="container">
      <div class="features__header reveal">
        <span class="features__eyebrow">Fonctionnalités</span>
        <h2 class="features__h2">Tout ce qu'il faut.<br><em>Rien de superflu.</em></h2>
        <p class="features__intro">
          BetterLeads est conçu pour les coachs — pas pour les développeurs.
          Simple à installer, puissant à l'usage.
        </p>
      </div>

      <div class="features__grid">
        <div
          v-for="(feat, i) in features"
          :key="feat.title"
          :class="['features__card', `reveal reveal-delay-${(i % 3) + 1}`, feat.highlight ? 'features__card--highlight' : '']"
        >
          <div class="features__icon" :style="{ background: feat.iconBg }">
            <span v-html="feat.icon"></span>
          </div>
          <h3 class="features__title">{{ feat.title }}</h3>
          <p class="features__desc">{{ feat.desc }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const features = [
  {
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/><polyline points="10 9 9 9 8 9"/></svg>`,
    iconBg: '#e8f0ec',
    title: 'Formulaire sur mesure',
    desc: 'Questions adaptées à votre type de coaching. Chaque coach a ses propres critères de qualification — on s\'adapte.',
    highlight: false,
  },
  {
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>`,
    iconBg: '#fdf6e3',
    title: 'Scoring automatique',
    desc: 'Chaque réponse est pondérée. Le système décide en 0,1 seconde si le prospect mérite votre temps.',
    highlight: true,
  },
  {
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>`,
    iconBg: '#e8f0ec',
    title: 'Emails automatiques',
    desc: 'Bonne réponse au bon prospect : enthousiaste pour les profils chauds, poli pour les autres.',
    highlight: false,
  },
  {
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>`,
    iconBg: '#f0ecf8',
    title: 'Calendrier conditionnel',
    desc: 'Seuls les prospects qualifiés voient votre lien Calendly. Les autres reçoivent un message d\'attente.',
    highlight: false,
  },
  {
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>`,
    iconBg: '#fdf6e3',
    title: 'Notifications instantanées',
    desc: 'Vous êtes alerté dès qu\'un prospect "chaud" arrive. Ne laissez plus passer une opportunité.',
    highlight: false,
  },
  {
    icon: `<svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>`,
    iconBg: '#e8f0ec',
    title: 'Installation en 2 minutes',
    desc: 'Une ligne de code sur votre site WordPress, Squarespace ou Wix. Aucune compétence technique requise.',
    highlight: false,
  },
]
</script>

<style scoped>
.features { background: var(--cream); }

.features__header {
  text-align: center;
  max-width: 560px;
  margin: 0 auto 64px;
}
.features__eyebrow {
  display: inline-block;
  font-size: .75rem;
  font-weight: 600;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin-bottom: 14px;
}
.features__h2 {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  line-height: 1.15;
  letter-spacing: -.02em;
  color: var(--ink);
  margin-bottom: 16px;
}
.features__h2 em { font-style: italic; color: var(--green); }
.features__intro {
  font-size: .95rem;
  color: var(--ink-muted);
  line-height: 1.7;
}

.features__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.features__card {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 28px;
  transition: transform .2s, box-shadow .2s;
}
.features__card:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-md);
}
.features__card--highlight {
  border-color: var(--green);
  background: linear-gradient(135deg, #f4faf7 0%, var(--white) 100%);
}

.features__icon {
  width: 48px;
  height: 48px;
  border-radius: var(--radius-md);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 18px;
  color: var(--green);
}
.features__title {
  font-family: var(--font-display);
  font-size: 1.05rem;
  color: var(--ink);
  margin-bottom: 8px;
}
.features__desc {
  font-size: .875rem;
  color: var(--ink-muted);
  line-height: 1.65;
}

@media (max-width: 900px) {
  .features__grid { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 560px) {
  .features__grid { grid-template-columns: 1fr; }
}
</style>
