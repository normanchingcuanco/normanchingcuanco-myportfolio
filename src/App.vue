<template>
  <!-- Root Layout -->
  <Navbar />
  <Landing />
  <Projects />
  <Tools />
  <Contact />
  <FooterSection />
</template>

<script setup>
import Navbar from './components/Navbar.vue'

/* ===============================
   FIX NOTE:
   Updated import to match actual filename:
   LandingPage.vue instead of About.vue
================================ */

import Landing from './components/Landing.vue'

import Projects from './components/Projects.vue'
import Tools from './components/Tools.vue'
import Contact from './components/Contact.vue'
import FooterSection from './components/Footer.vue'
</script>