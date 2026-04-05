<template>
  <NavBar />
  <HeroSection />
  <BeforeAfter />
  <FeaturesSection />
  <HowItWorks />
  <TestimonialsSection />
  <PricingSection />
  <CtaFooter />
</template>

<script setup>
import { onMounted, nextTick } from 'vue'
import NavBar             from './components/NavBar.vue'
import HeroSection        from './components/HeroSection.vue'
import BeforeAfter        from './components/BeforeAfter.vue'
import FeaturesSection    from './components/FeaturesSection.vue'
import HowItWorks         from './components/HowItWorks.vue'
import TestimonialsSection from './components/TestimonialsSection.vue'
import PricingSection     from './components/PricingSection.vue'
import CtaFooter          from './components/CtaFooter.vue'
import { useReveal }      from './composables/useReveal.js'

onMounted(async () => {
  await nextTick()
  useReveal()
})
</script>
