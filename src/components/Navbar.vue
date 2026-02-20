<template>
  <!-- NAVBAR -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top premium-navbar">
    <div class="container">

      <!-- Brand -->
      <a class="navbar-brand premium-brand" href="#landing">
        MyPortfolio
      </a>

      <!-- Hamburger -->
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navlinks"
        aria-controls="navlinks"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <!-- Collapsible Menu -->
      <div
        class="collapse navbar-collapse"
        id="navlinks"
        ref="navCollapse"
      >
        <ul class="navbar-nav ms-auto premium-navlinks">

          <li class="nav-item">
            <a class="nav-link" href="#landing" @click="closeMenu">
              Home
            </a>
          </li>

          <li class="nav-item">
            <a class="nav-link" href="#projects" @click="closeMenu">
              My Projects
            </a>
          </li>

          <li class="nav-item">
            <a class="nav-link" href="#tools" @click="closeMenu">
              Tools
            </a>
          </li>

          <li class="nav-item">
            <a class="nav-link" href="#contact" @click="closeMenu">
              Contact
            </a>
          </li>

        </ul>
      </div>

    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue"
import Collapse from "bootstrap/js/dist/collapse"

const navCollapse = ref(null)

function closeMenu() {
  if (!navCollapse.value) return

  // Check if collapse is open
  if (navCollapse.value.classList.contains("show")) {

    // Create or get instance safely
    const bsCollapse =
      Collapse.getInstance(navCollapse.value) ||
      new Collapse(navCollapse.value)

    bsCollapse.hide()
  }
}
</script>