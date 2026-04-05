<template>
  <section class="cta-final">
    <div class="container">
      <div class="cta-final__inner reveal">
        <span class="cta-final__eyebrow">Prêt à commencer ?</span>
        <h2 class="cta-final__h2">
          Vos prochains clients<br>
          méritent mieux qu'un email <em>sans réponse.</em>
        </h2>
        <p class="cta-final__sub">
          Rejoignez les coachs qui qualifient leurs prospects automatiquement.
          Installation en 2 minutes. Résultats dès le premier jour.
        </p>
        <div class="cta-final__actions">
          <a href="mailto:hello@betterleads.io" class="btn btn-primary cta-final__btn">
            Demander une démo gratuite
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
          </a>
          <p class="cta-final__note">Réponse sous 24h · Démo personnalisée · Sans engagement</p>
        </div>
      </div>
    </div>
  </section>

  <footer class="footer">
    <div class="container footer__inner">
      <div class="footer__brand">
        <div class="footer__logo">
          <span class="footer__logo-mark">B</span>
          <span class="footer__logo-text">BetterLeads</span>
        </div>
        <p class="footer__tagline">
          Le système de qualification automatique<br>pour les coachs sérieux.
        </p>
      </div>

      <div class="footer__links">
        <div class="footer__col">
          <p class="footer__col-title">Produit</p>
          <a href="#features">Fonctionnalités</a>
          <a href="#how">Comment ça marche</a>
          <a href="#pricing">Tarifs</a>
        </div>
        <div class="footer__col">
          <p class="footer__col-title">Contact</p>
          <a href="mailto:hello@betterleads.io">hello@betterleads.io</a>
          <a href="#">Demander une démo</a>
        </div>
      </div>
    </div>

    <div class="container footer__bottom">
      <p>© 2026 BetterLeads · Tous droits réservés</p>
      <div class="footer__legal">
        <a href="#">Mentions légales</a>
        <a href="#">Politique de confidentialité</a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
/* ── CTA Final ── */
.cta-final {
  background: var(--green);
  padding: 96px 0;
  position: relative;
  overflow: hidden;
}
.cta-final::before {
  content: '';
  position: absolute;
  inset: 0;
  background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Ccircle cx='30' cy='30' r='2'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}

.cta-final__inner {
  text-align: center;
  position: relative;
  max-width: 680px;
  margin: 0 auto;
}

.cta-final__eyebrow {
  display: inline-block;
  font-size: .75rem;
  font-weight: 600;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: rgba(255,255,255,.5);
  margin-bottom: 20px;
}

.cta-final__h2 {
  font-family: var(--font-display);
  font-size: clamp(1.9rem, 4vw, 3rem);
  line-height: 1.15;
  letter-spacing: -.02em;
  color: #fff;
  margin-bottom: 20px;
}
.cta-final__h2 em {
  font-style: italic;
  color: var(--gold);
}

.cta-final__sub {
  font-size: 1rem;
  color: rgba(255,255,255,.7);
  line-height: 1.7;
  margin-bottom: 36px;
}

.cta-final__actions { display: flex; flex-direction: column; align-items: center; gap: 14px; }

.cta-final__btn {
  background: #fff;
  color: var(--green);
  font-size: 1rem;
  padding: 16px 36px;
  box-shadow: 0 4px 20px rgba(0,0,0,.2);
}
.cta-final__btn:hover {
  background: #f4faf7;
  transform: translateY(-2px);
  box-shadow: 0 8px 32px rgba(0,0,0,.25);
}

.cta-final__note {
  font-size: .78rem;
  color: rgba(255,255,255,.45);
}

/* ── Footer ── */
.footer {
  background: var(--ink);
  color: var(--ink-muted);
  padding-top: 64px;
}

.footer__inner {
  display: grid;
  grid-template-columns: 1.5fr 1fr;
  gap: 80px;
  padding-bottom: 48px;
  border-bottom: 1px solid #2a2a28;
}

.footer__brand { display: flex; flex-direction: column; gap: 16px; }

.footer__logo {
  display: flex;
  align-items: center;
  gap: 10px;
}
.footer__logo-mark {
  width: 32px;
  height: 32px;
  background: var(--green);
  color: #fff;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 1.1rem;
}
.footer__logo-text {
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 1.1rem;
  color: #fff;
}

.footer__tagline {
  font-size: .85rem;
  line-height: 1.6;
  color: #555;
}

.footer__links { display: grid; grid-template-columns: repeat(2, 1fr); gap: 32px; }

.footer__col {
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.footer__col-title {
  font-size: .72rem;
  font-weight: 700;
  letter-spacing: .08em;
  text-transform: uppercase;
  color: #777;
  margin-bottom: 4px;
}
.footer__col a {
  font-size: .85rem;
  color: #555;
  transition: color .15s;
}
.footer__col a:hover { color: #fff; }

.footer__bottom {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 24px;
  font-size: .78rem;
}
.footer__legal { display: flex; gap: 24px; }
.footer__legal a { color: #444; transition: color .15s; }
.footer__legal a:hover { color: #fff; }

@media (max-width: 768px) {
  .footer__inner { grid-template-columns: 1fr; gap: 40px; }
  .footer__bottom { flex-direction: column; gap: 12px; text-align: center; }
  .cta-final { padding: 72px 0; }
}
</style>
