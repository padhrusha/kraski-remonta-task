<script setup>
import AppHeader from './components/AppHeader.vue'
import HeroSection from './components/HeroSection.vue'
import DisputesSection from './components/DisputesSection.vue'
import OffersSection from './components/OffersSection.vue'
import FaqSection from './components/FaqSection.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="page-top">
    <AppHeader />
    <HeroSection />
  </div>
  <main>
    <DisputesSection />
    <OffersSection />
    <FaqSection />
  </main>
  <AppFooter />
</template>

<style lang="scss" scoped>
.page-top {
  position: relative;
}
</style>
