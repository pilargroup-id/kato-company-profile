<script setup>
import AppHeader from "./components/AppHeader.vue";
import HeroSection from "./components/HeroSection.vue";
import BenefitStrip from "./components/BenefitStrip.vue";
import AboutSection from "./components/AboutSection.vue";
import BrandsCarousel from "./components/BrandsCarousel.vue";
import ContactSection from "./components/ContactSection.vue";
import AppFooter from "./components/AppFooter.vue";
import FloatingWhatsApp from "./components/FloatingWhatsApp.vue";
</script>

<template>
  <div class="site-shell">
    <AppHeader />
    <main>
      <HeroSection />
      <BenefitStrip />
      <AboutSection />
      <BrandsCarousel />
      <ContactSection />
    </main>
    <AppFooter />
    <FloatingWhatsApp />
  </div>
</template>
