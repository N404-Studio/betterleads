<template>
  <section class="testimonials">
    <div class="container">
      <div class="testimonials__header reveal">
        <span class="testimonials__eyebrow">Témoignages</span>
        <h2 class="testimonials__h2">Ce qu'ils en <em>disent.</em></h2>
      </div>

      <div class="testimonials__grid">
        <div
          v-for="(t, i) in testimonials"
          :key="t.name"
          :class="`testimonials__card reveal reveal-delay-${(i % 3) + 1}`"
        >
          <div class="testimonials__stars">
            <svg v-for="n in 5" :key="n" width="14" height="14" viewBox="0 0 24 24" fill="var(--gold)" stroke="none"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"/></svg>
          </div>
          <blockquote class="testimonials__quote">{{ t.quote }}</blockquote>
          <div class="testimonials__author">
            <div class="testimonials__avatar" :style="{ background: t.avatarBg }">
              {{ t.name.charAt(0) }}
            </div>
            <div>
              <p class="testimonials__name">{{ t.name }}</p>
              <p class="testimonials__role">{{ t.role }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const testimonials = [
  {
    quote: "En une semaine, j'ai arrêté de répondre à des emails non pertinents. Mes appels sont désormais tous des conversations sérieuses. Le ROI est immédiat.",
    name: 'Sophie M.',
    role: 'Coach de vie & reconversion',
    avatarBg: '#c9e8d8',
  },
  {
    quote: "J'avais peur que mes prospects trouvent ça froid. Au contraire, ils me disent que c'est professionnel. Le widget crédibilise vraiment ma démarche.",
    name: 'Thomas R.',
    role: 'Coach business & entrepreneur',
    avatarBg: '#fde8c9',
  },
  {
    quote: "Avant, je donnais accès à mon Calendly à tout le monde. Maintenant, seuls 30% de mes demandes arrivent à l'étape appel — et ce sont les 30% qui comptent.",
    name: 'Amélie D.',
    role: 'Coach immobilier certifiée',
    avatarBg: '#c9d8f0',
  },
  {
    quote: "L'installation sur WordPress m'a pris littéralement 3 minutes. Je ne m'attendais pas à quelque chose d'aussi simple.",
    name: 'Laurent K.',
    role: 'Coach sportif & performance',
    avatarBg: '#f0c9d8',
  },
  {
    quote: "Ce que j'aime, c'est que le système dit non à ma place. Je n'ai plus à gérer le malaise de refuser quelqu'un.",
    name: 'Nathalie B.',
    role: 'Coach bien-être & mindfulness',
    avatarBg: '#d8f0c9',
  },
  {
    quote: "BetterLeads m'a permis de passer de 5 appels inutiles par semaine à 0. Et mes appels utiles, eux, ont doublé.",
    name: 'Marc V.',
    role: 'Coach financier & investissement',
    avatarBg: '#f0e8c9',
  },
]
</script>

<style scoped>
.testimonials { background: var(--cream); }

.testimonials__header {
  text-align: center;
  margin-bottom: 64px;
}
.testimonials__eyebrow {
  display: inline-block;
  font-size: .75rem;
  font-weight: 600;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin-bottom: 14px;
}
.testimonials__h2 {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  line-height: 1.15;
  letter-spacing: -.02em;
  color: var(--ink);
}
.testimonials__h2 em { font-style: italic; color: var(--green); }

.testimonials__grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.testimonials__card {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 28px;
  display: flex;
  flex-direction: column;
  gap: 16px;
  transition: transform .2s, box-shadow .2s;
}
.testimonials__card:hover {
  transform: translateY(-3px);
  box-shadow: var(--shadow-md);
}

.testimonials__stars { display: flex; gap: 3px; }

.testimonials__quote {
  font-family: var(--font-display);
  font-style: italic;
  font-size: .95rem;
  color: var(--ink-soft);
  line-height: 1.7;
  flex: 1;
}
.testimonials__quote::before { content: '\201C'; }
.testimonials__quote::after  { content: '\201D'; }

.testimonials__author {
  display: flex;
  align-items: center;
  gap: 12px;
  border-top: 1px solid var(--border);
  padding-top: 16px;
}
.testimonials__avatar {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 1rem;
  color: var(--ink);
  flex-shrink: 0;
}
.testimonials__name {
  font-size: .875rem;
  font-weight: 600;
  color: var(--ink);
}
.testimonials__role {
  font-size: .78rem;
  color: var(--ink-muted);
}

@media (max-width: 900px) {
  .testimonials__grid { grid-template-columns: repeat(2, 1fr); }
}
@media (max-width: 560px) {
  .testimonials__grid { grid-template-columns: 1fr; }
}
</style>
