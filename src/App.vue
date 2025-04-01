<template>
  <div class="container">
    <AppHeader />
    <OverviewSection />
    <StepsSection />
    <FaqSection />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import OverviewSection from './components/OverviewSection.vue'
import StepsSection from './components/StepsSection.vue'
import FaqSection from './components/FaqSection.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    OverviewSection,
    StepsSection,
    FaqSection,
    AppFooter
  }
}
</script> 