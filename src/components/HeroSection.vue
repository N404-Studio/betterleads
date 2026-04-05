<template>
  <section class="hero">
    <div class="container hero__inner">

      <!-- Left: copy -->
      <div class="hero__copy">
        <div class="hero__badge reveal">
          <span class="hero__badge-dot"></span>
          Nouveau · Widget de pré-qualification
        </div>

        <h1 class="hero__h1 reveal reveal-delay-1">
          Arrêtez de perdre<br>
          <em>votre temps</em><br>
          en appels inutiles.
        </h1>

        <p class="hero__sub reveal reveal-delay-2">
          BetterLeads installe un formulaire intelligent sur votre site.
          Vos prospects sont qualifiés automatiquement — seuls les bons
          arrivent dans votre calendrier.
        </p>

        <div class="hero__actions reveal reveal-delay-3">
          <a href="#demo" class="btn btn-primary">
            Voir comment ça marche
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
          </a>
          <a href="#pricing" class="btn btn-ghost">Voir les tarifs</a>
        </div>

        <div class="hero__proof reveal reveal-delay-4">
          <div class="hero__avatars">
            <div class="hero__avatar" style="background:#c9e8d8">M</div>
            <div class="hero__avatar" style="background:#fde8c9">S</div>
            <div class="hero__avatar" style="background:#c9d8f0">L</div>
            <div class="hero__avatar" style="background:#f0c9d8">A</div>
          </div>
          <p class="hero__proof-text">
            <strong>+40 coachs</strong> ont déjà intégré BetterLeads sur leur site
          </p>
        </div>
      </div>

      <!-- Right: widget mockup -->
      <div class="hero__visual reveal reveal-delay-2">
        <div class="hero__mockup">
          <div class="hero__mockup-bar">
            <span></span><span></span><span></span>
          </div>
          <div class="hero__mockup-body">
            <p class="hero__mock-label">Étape 1 / 4 · 25%</p>
            <div class="hero__mock-progress">
              <div class="hero__mock-fill"></div>
            </div>
            <h3 class="hero__mock-title">Un premier échange ?</h3>
            <p class="hero__mock-sub">Quelques questions — 2 minutes.</p>

            <div class="hero__mock-field">
              <label>Votre prénom</label>
              <div class="hero__mock-input">Sophie</div>
            </div>
            <div class="hero__mock-field">
              <label>Sur quoi souhaitez-vous travailler ?</label>
              <div class="hero__mock-options">
                <div class="hero__mock-opt is-sel">Reconversion professionnelle</div>
                <div class="hero__mock-opt">Gestion du stress</div>
                <div class="hero__mock-opt">Confiance en soi</div>
              </div>
            </div>
            <div class="hero__mock-btn">
              Suivant
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
            </div>
          </div>
          <!-- Mockup top-left dots need border-radius fix since no overflow:hidden -->
        </div>
        <!-- Score badge is sibling of mockup, positioned relative to .hero__visual -->
        <div class="hero__score-badge">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
          Score 8/10 — Prospect qualifié
        </div>
      </div>

    </div>

    <!-- Background decoration -->
    <div class="hero__deco" aria-hidden="true">
      <div class="hero__deco-circle hero__deco-circle--1"></div>
      <div class="hero__deco-circle hero__deco-circle--2"></div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue'
import { useReveal } from '../composables/useReveal.js'
onMounted(() => useReveal())
</script>

<style scoped>
.hero {
  padding-top: 140px;
  padding-bottom: 96px;
  position: relative;
  overflow: hidden;
}
.hero__inner {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
}

/* ── Copy ── */
.hero__badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 6px 14px;
  background: var(--green-light);
  color: var(--green);
  border-radius: var(--radius-pill);
  font-size: .78rem;
  font-weight: 600;
  letter-spacing: .03em;
  text-transform: uppercase;
  margin-bottom: 24px;
}
.hero__badge-dot {
  width: 7px;
  height: 7px;
  background: var(--green);
  border-radius: 50%;
  animation: pulse 2s infinite;
}
@keyframes pulse {
  0%,100% { opacity: 1; transform: scale(1); }
  50%      { opacity: .5; transform: scale(1.4); }
}

.hero__h1 {
  font-family: var(--font-display);
  font-size: clamp(2.4rem, 4.5vw, 3.6rem);
  line-height: 1.1;
  letter-spacing: -.02em;
  color: var(--ink);
  margin-bottom: 24px;
}
.hero__h1 em {
  font-style: italic;
  color: var(--green);
}

.hero__sub {
  font-size: 1.05rem;
  color: var(--ink-soft);
  line-height: 1.7;
  max-width: 440px;
  margin-bottom: 36px;
}

.hero__actions {
  display: flex;
  align-items: center;
  gap: 12px;
  flex-wrap: wrap;
  margin-bottom: 40px;
}

.hero__proof { display: flex; align-items: center; gap: 14px; }
.hero__avatars { display: flex; }
.hero__avatar {
  width: 34px;
  height: 34px;
  border-radius: 50%;
  border: 2px solid var(--cream);
  font-family: var(--font-display);
  font-size: .85rem;
  font-weight: 700;
  display: flex;
  align-items: center;
  justify-content: center;
  color: var(--ink);
  margin-left: -8px;
}
.hero__avatars .hero__avatar:first-child { margin-left: 0; }
.hero__proof-text { font-size: .82rem; color: var(--ink-muted); }
.hero__proof-text strong { color: var(--ink); }

/* ── Widget mockup ── */
.hero__visual {
  position: relative;
  /* Padding to give the overflowing badge room without clipping */
  padding-bottom: 32px;
  padding-right: 20px;
}
.hero__mockup {
  background: var(--white);
  border: 1px solid var(--border);
  border-radius: 20px;
  box-shadow: var(--shadow-lg);
  /* overflow: hidden removed — was clipping the score badge */
  position: relative;
}
.hero__mockup-bar {
  display: flex;
  gap: 6px;
  padding: 14px 18px;
  background: #f5f3ee;
  border-bottom: 1px solid var(--border);
  /* Replicate top radius since overflow:hidden is removed */
  border-radius: 20px 20px 0 0;
}
.hero__mockup-bar span {
  width: 10px; height: 10px;
  border-radius: 50%;
  background: var(--border);
}
.hero__mockup-bar span:nth-child(1) { background: #ff6058; }
.hero__mockup-bar span:nth-child(2) { background: #ffbd2e; }
.hero__mockup-bar span:nth-child(3) { background: #28c840; }

.hero__mockup-body { padding: 28px 28px 32px; }

.hero__mock-label {
  font-size: .72rem;
  color: var(--ink-muted);
  font-family: var(--font-body);
  margin-bottom: 6px;
}
.hero__mock-progress {
  height: 3px;
  background: #eee;
  border-radius: 99px;
  margin-bottom: 24px;
  overflow: hidden;
}
.hero__mock-fill {
  width: 25%;
  height: 100%;
  background: var(--green);
  border-radius: 99px;
}
.hero__mock-title {
  font-family: var(--font-display);
  font-size: 1.25rem;
  color: var(--ink);
  margin-bottom: 4px;
}
.hero__mock-sub {
  font-size: .8rem;
  color: var(--ink-muted);
  margin-bottom: 20px;
}
.hero__mock-field { margin-bottom: 16px; }
.hero__mock-field label {
  display: block;
  font-size: .78rem;
  font-weight: 600;
  color: var(--ink-soft);
  margin-bottom: 6px;
}
.hero__mock-input {
  padding: 10px 14px;
  border: 1.5px solid var(--border);
  border-radius: 10px;
  font-size: .85rem;
  color: var(--ink);
  background: var(--cream);
}
.hero__mock-options { display: flex; flex-direction: column; gap: 7px; }
.hero__mock-opt {
  padding: 10px 14px;
  border: 1.5px solid var(--border);
  border-radius: 10px;
  font-size: .82rem;
  color: var(--ink-soft);
  cursor: pointer;
  transition: all .15s;
}
.hero__mock-opt.is-sel {
  border-color: var(--green);
  background: var(--green-light);
  color: var(--green);
  font-weight: 600;
}
.hero__mock-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 6px;
  margin-top: 20px;
  padding: 12px;
  background: var(--green);
  color: #fff;
  border-radius: var(--radius-pill);
  font-size: .85rem;
  font-weight: 600;
}

.hero__score-badge {
  position: absolute;
  /* Sits just below the mockup's bottom-right corner.
     hero__visual has padding-bottom:32px so the badge floats
     visually anchored to the card without being clipped. */
  bottom: 0;
  right: 0;
  background: var(--green);
  color: #fff;
  padding: 10px 16px;
  border-radius: var(--radius-pill);
  font-size: .78rem;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 6px;
  box-shadow: 0 4px 16px rgba(26,92,69,.35);
  white-space: nowrap;
}

/* ── Deco ── */
.hero__deco { position: absolute; inset: 0; pointer-events: none; z-index: -1; }
.hero__deco-circle {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  opacity: .35;
}
.hero__deco-circle--1 {
  width: 500px; height: 500px;
  background: var(--green-light);
  top: -100px; right: -100px;
}
.hero__deco-circle--2 {
  width: 300px; height: 300px;
  background: var(--gold-light);
  bottom: -50px; left: 20%;
}

@media (max-width: 900px) {
  .hero__inner { grid-template-columns: 1fr; gap: 56px; }
  .hero__visual { order: -1; max-width: 440px; margin: 0 auto; width: 100%; }
  .hero__score-badge { bottom: 0; right: 0; }
}
</style>
