<template>
  <section class="ba" id="problem">
    <div class="container">
      <div class="ba__header reveal">
        <span class="ba__eyebrow">Le problème</span>
        <h2 class="ba__h2">Vous passez vos journées à trier,<br><em>pas à coacher.</em></h2>
      </div>

      <div class="ba__grid">
        <!-- Before -->
        <div class="ba__card ba__card--before reveal reveal-delay-1">
          <div class="ba__card-tag ba__card-tag--red">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
            Avant BetterLeads
          </div>
          <h3 class="ba__card-title">Le coach débordé</h3>
          <ul class="ba__list ba__list--bad">
            <li v-for="item in before" :key="item">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
              {{ item }}
            </li>
          </ul>
        </div>

        <!-- Arrow -->
        <div class="ba__arrow reveal reveal-delay-2">
          <svg width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="var(--green)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
        </div>

        <!-- After -->
        <div class="ba__card ba__card--after reveal reveal-delay-3">
          <div class="ba__card-tag ba__card-tag--green">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
            Avec BetterLeads
          </div>
          <h3 class="ba__card-title">Le coach serein</h3>
          <ul class="ba__list ba__list--good">
            <li v-for="item in after" :key="item">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
              {{ item }}
            </li>
          </ul>
        </div>
      </div>

      <!-- Stat strip -->
      <div class="ba__stats reveal reveal-delay-2">
        <div class="ba__stat" v-for="stat in stats" :key="stat.value">
          <span class="ba__stat-value">{{ stat.value }}</span>
          <span class="ba__stat-label">{{ stat.label }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const before = [
  'Vous recevez des demandes non qualifiées',
  'Vous passez 30 min à répondre à chaque email',
  'Des inconnus réservent directement dans votre agenda',
  'Vous faites des appels pour rien 2 fois par semaine',
  'Vous n\'osez pas refuser par manque de système',
]
const after = [
  'Seuls les prospects sérieux passent le filtre',
  'Le formulaire répond à leur place, automatiquement',
  'Votre calendrier ne s\'ouvre qu\'aux personnes qualifiées',
  'Vos appels sont tous pertinents et préparés',
  'Le système dit non poliment — sans vous impliquer',
]
const stats = [
  { value: '3×', label: 'plus de conversions appel → client' },
  { value: '–70%', label: 'de temps perdu en triage' },
  { value: '2 min', label: 'pour installer le widget' },
]
</script>

<style scoped>
.ba { background: var(--white); }

.ba__header {
  text-align: center;
  margin-bottom: 64px;
}
.ba__eyebrow {
  display: inline-block;
  font-size: .75rem;
  font-weight: 600;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin-bottom: 14px;
}
.ba__h2 {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  line-height: 1.15;
  letter-spacing: -.02em;
  color: var(--ink);
}
.ba__h2 em { font-style: italic; color: var(--green); }

.ba__grid {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  gap: 24px;
  align-items: start;
  margin-bottom: 56px;
}
.ba__arrow {
  display: flex;
  align-items: center;
  justify-content: center;
  padding-top: 120px;
}

.ba__card {
  border-radius: var(--radius-lg);
  padding: 32px;
  border: 1px solid var(--border);
}
.ba__card--before {
  background: #fff8f8;
  border-color: #fde0e0;
}
.ba__card--after {
  background: #f4faf7;
  border-color: #c9e8d8;
}

.ba__card-tag {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  font-size: .75rem;
  font-weight: 700;
  letter-spacing: .06em;
  text-transform: uppercase;
  padding: 5px 12px;
  border-radius: var(--radius-pill);
  margin-bottom: 16px;
}
.ba__card-tag--red   { background: #fde0e0; color: #c0392b; }
.ba__card-tag--green { background: var(--green-light); color: var(--green); }

.ba__card-title {
  font-family: var(--font-display);
  font-size: 1.2rem;
  color: var(--ink);
  margin-bottom: 20px;
}

.ba__list { list-style: none; display: flex; flex-direction: column; gap: 12px; }
.ba__list li {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  font-size: .9rem;
  line-height: 1.5;
}
.ba__list li svg { flex-shrink: 0; margin-top: 2px; }
.ba__list--bad  li        { color: var(--ink-soft); }
.ba__list--bad  li svg    { color: #e74c3c; }
.ba__list--good li        { color: var(--ink-soft); }
.ba__list--good li svg    { color: var(--green); }

/* Stat strip */
.ba__stats {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  overflow: hidden;
}
.ba__stat {
  background: var(--cream);
  padding: 32px 24px;
  text-align: center;
}
.ba__stat-value {
  display: block;
  font-family: var(--font-display);
  font-size: 2.4rem;
  font-weight: 700;
  color: var(--green);
  line-height: 1;
  margin-bottom: 8px;
}
.ba__stat-label {
  font-size: .82rem;
  color: var(--ink-muted);
  line-height: 1.4;
}

@media (max-width: 768px) {
  .ba__grid { grid-template-columns: 1fr; }
  .ba__arrow { padding-top: 0; transform: rotate(90deg); justify-self: center; }
  .ba__stats { grid-template-columns: 1fr; }
}
</style>
