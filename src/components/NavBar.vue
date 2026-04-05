<template>
  <header :class="['nav', { 'nav--scrolled': scrolled }]">
    <div class="container nav__inner">
      <a href="#" class="nav__logo">
        <span class="nav__logo-mark">B</span>
        <span class="nav__logo-text">BetterLeads</span>
      </a>

      <nav class="nav__links">
        <a href="#features">Fonctionnalités</a>
        <a href="#how">Comment ça marche</a>
        <a href="#pricing">Tarifs</a>
      </nav>

      <a href="#demo" class="btn btn-primary nav__cta">
        Voir la démo
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"/></svg>
      </a>

      <!-- Mobile burger -->
      <button class="nav__burger" @click="mobileOpen = !mobileOpen" :aria-expanded="mobileOpen">
        <span></span><span></span><span></span>
      </button>
    </div>

    <!-- Mobile menu -->
    <div :class="['nav__mobile', { 'is-open': mobileOpen }]">
      <a href="#features" @click="mobileOpen = false">Fonctionnalités</a>
      <a href="#how"      @click="mobileOpen = false">Comment ça marche</a>
      <a href="#pricing"  @click="mobileOpen = false">Tarifs</a>
      <a href="#demo"     @click="mobileOpen = false" class="btn btn-primary" style="margin-top:8px">Voir la démo</a>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
const scrolled    = ref(false)
const mobileOpen  = ref(false)

function onScroll() { scrolled.value = window.scrollY > 40 }
onMounted(()  => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<style scoped>
.nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 100;
  transition: background .3s, box-shadow .3s;
  padding: 0;
}
.nav--scrolled {
  background: rgba(250,248,243,.92);
  backdrop-filter: blur(12px);
  box-shadow: 0 1px 0 var(--border);
}
.nav__inner {
  display: flex;
  align-items: center;
  height: 68px;
  gap: 40px;
}
.nav__logo {
  display: flex;
  align-items: center;
  gap: 10px;
  flex-shrink: 0;
}
.nav__logo-mark {
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
.nav__logo-text {
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 1.1rem;
  color: var(--ink);
  letter-spacing: -.01em;
}
.nav__links {
  display: flex;
  align-items: center;
  gap: 32px;
  flex: 1;
}
.nav__links a {
  font-size: .875rem;
  font-weight: 500;
  color: var(--ink-soft);
  transition: color .15s;
}
.nav__links a:hover { color: var(--green); }
.nav__cta { margin-left: auto; }

.nav__burger {
  display: none;
  flex-direction: column;
  gap: 5px;
  padding: 8px;
  margin-left: auto;
}
.nav__burger span {
  display: block;
  width: 22px;
  height: 2px;
  background: var(--ink);
  border-radius: 2px;
  transition: all .2s;
}
.nav__mobile {
  display: none;
  flex-direction: column;
  padding: 16px 24px 24px;
  background: var(--cream);
  border-top: 1px solid var(--border);
  gap: 4px;
}
.nav__mobile.is-open { display: flex; }
.nav__mobile a {
  padding: 10px 12px;
  font-size: .9rem;
  font-weight: 500;
  color: var(--ink-soft);
  border-radius: var(--radius-sm);
}
.nav__mobile a:hover { background: var(--green-light); color: var(--green); }

@media (max-width: 768px) {
  .nav__links, .nav__cta { display: none; }
  .nav__burger { display: flex; }
}
</style>
