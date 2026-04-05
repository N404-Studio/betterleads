<template>
  <section class="how" id="how">
    <div class="container">
      <div class="how__header reveal">
        <span class="how__eyebrow">Comment ça marche</span>
        <h2 class="how__h2">En place en <em>3 étapes.</em></h2>
      </div>

      <div class="how__steps">
        <div
          v-for="(step, i) in steps"
          :key="step.title"
          :class="`how__step reveal reveal-delay-${i + 1}`"
        >
          <div class="how__step-num">{{ String(i + 1).padStart(2, '0') }}</div>
          <div class="how__step-icon" v-html="step.icon"></div>
          <h3 class="how__step-title">{{ step.title }}</h3>
          <p class="how__step-desc">{{ step.desc }}</p>
        </div>
      </div>

      <!-- Demo embed mockup -->
      <div class="how__embed reveal reveal-delay-2" id="demo">
        <div class="how__embed-label">Le code que votre client colle sur son site</div>
        <div class="how__embed-code">
          <span class="tok-tag">&lt;div</span>
          <span class="tok-attr"> id</span><span class="tok-eq">=</span><span class="tok-str">"pq-widget"</span>
          <span class="tok-tag">&gt;&lt;/div&gt;</span>
          <br/>
          <span class="tok-tag">&lt;script</span>
          <span class="tok-attr"> src</span><span class="tok-eq">=</span><span class="tok-str">"https://betterleads.io/widget.js"</span>
          <br/>
          <span class="tok-attr" style="padding-left:2.5rem"> data-client</span><span class="tok-eq">=</span><span class="tok-str">"karine_galland"</span>
          <br/>
          <span class="tok-attr" style="padding-left:2.5rem"> data-token</span><span class="tok-eq">=</span><span class="tok-str">"sk_•••••••••"</span>
          <span class="tok-tag">&gt;&lt;/script&gt;</span>
        </div>
        <div class="how__embed-footer">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><polyline points="20 6 9 17 4 12"/></svg>
          Compatible WordPress · Squarespace · Wix · tout site HTML
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const steps = [
  {
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M20 14.66V20a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h5.34"/><polygon points="18 2 22 6 12 16 8 16 8 12 18 2"/></svg>`,
    title: 'On configure votre formulaire',
    desc: 'Vous nous dites votre type de coaching, vos critères de sélection et l\'URL de votre Calendly. On s\'occupe du reste.',
  },
  {
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><polyline points="16 18 22 12 16 6"/><polyline points="8 6 2 12 8 18"/></svg>`,
    title: 'Vous collez 2 lignes sur votre site',
    desc: 'On vous envoie un snippet à copier-coller. Aucune compétence technique nécessaire — ça prend 2 minutes.',
  },
  {
    icon: `<svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/></svg>`,
    title: 'Le système filtre à votre place',
    desc: 'Dès qu\'un prospect remplit le formulaire, il est scoré, routé et reçoit un email. Vous n\'intervenez que pour les bons profils.',
  },
]
</script>

<style scoped>
.how { background: var(--white); }

.how__header {
  text-align: center;
  margin-bottom: 64px;
}
.how__eyebrow {
  display: inline-block;
  font-size: .75rem;
  font-weight: 600;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: var(--ink-muted);
  margin-bottom: 14px;
}
.how__h2 {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 3.5vw, 2.8rem);
  line-height: 1.15;
  letter-spacing: -.02em;
  color: var(--ink);
}
.how__h2 em { font-style: italic; color: var(--green); }

.how__steps {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 48px;
  margin-bottom: 72px;
  position: relative;
}
.how__steps::before {
  content: '';
  position: absolute;
  top: 28px;
  left: calc(16.66% + 24px);
  right: calc(16.66% + 24px);
  height: 1px;
  background: repeating-linear-gradient(90deg, var(--border) 0, var(--border) 6px, transparent 6px, transparent 14px);
}

.how__step { text-align: center; position: relative; }

.how__step-num {
  font-family: var(--font-display);
  font-size: 2.8rem;
  font-weight: 700;
  color: var(--green-light);
  line-height: 1;
  margin-bottom: 8px;
}

.how__step-icon {
  width: 56px;
  height: 56px;
  background: var(--green-light);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 20px;
  color: var(--green);
}

.how__step-title {
  font-family: var(--font-display);
  font-size: 1.1rem;
  color: var(--ink);
  margin-bottom: 10px;
}
.how__step-desc {
  font-size: .875rem;
  color: var(--ink-muted);
  line-height: 1.65;
}

/* Code embed */
.how__embed {
  background: #1a1a18;
  border-radius: var(--radius-lg);
  overflow: hidden;
  max-width: 680px;
  margin: 0 auto;
}
.how__embed-label {
  padding: 12px 24px;
  font-size: .72rem;
  font-weight: 600;
  letter-spacing: .06em;
  text-transform: uppercase;
  color: #666;
  border-bottom: 1px solid #2a2a28;
}
.how__embed-code {
  padding: 28px 28px;
  font-family: 'SF Mono', 'Fira Code', monospace;
  font-size: .82rem;
  line-height: 1.9;
  color: #d4d0c8;
}
.tok-tag  { color: #7ec8a0; }
.tok-attr { color: #9bc8f0; }
.tok-eq   { color: #d4d0c8; }
.tok-str  { color: #f0c97a; }

.how__embed-footer {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 12px 24px;
  background: #141412;
  font-size: .75rem;
  color: var(--green-mid);
  border-top: 1px solid #2a2a28;
}

@media (max-width: 768px) {
  .how__steps { grid-template-columns: 1fr; gap: 40px; }
  .how__steps::before { display: none; }
}
</style>
