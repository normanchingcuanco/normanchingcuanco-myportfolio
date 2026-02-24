<template>
  <!-- =========================================================
       SINGLE PROJECT CARD (UPDATED VERSION)
       Now supports:
       - Multiple links (Live + GitHub)
       - Custom button labels
       - Works for Short Courses + Projects
       - Backward compatible with old structure
       - UPDATED: Supports tertiary & quaternary links
  ========================================================== -->

  <div class="project-card">
    <div class="project-img-wrapper">
      <img
        :src="project.image"
        :alt="project.title"
      >
    </div>

    <div class="project-body">
      <h5>{{ project.title }}</h5>

      <p class="project-desc">
        {{ project.description }}
      </p>

      <!-- PRIMARY LINK -->
      <a
        v-if="project.primaryLink"
        :href="project.primaryLink"
        target="_blank"
        class="project-link"
      >
        {{ project.primaryLabel || "View Project →" }}
      </a>

      <!-- SECONDARY LINK -->
      <a
        v-if="project.secondaryLink"
        :href="project.secondaryLink"
        target="_blank"
        class="project-link"
      >
        {{ project.secondaryLabel || "View GitHub →" }}
      </a>

      <!-- NEW: TERTIARY LINK -->
      <a
        v-if="project.tertiaryLink"
        :href="project.tertiaryLink"
        target="_blank"
        class="project-link"
      >
        {{ project.tertiaryLabel }}
      </a>

      <!-- NEW: QUATERNARY LINK -->
      <a
        v-if="project.quaternaryLink"
        :href="project.quaternaryLink"
        target="_blank"
        class="project-link"
      >
        {{ project.quaternaryLabel }}
      </a>

      <!-- BACKWARD COMPATIBILITY -->
      <a
        v-if="project.link && !project.primaryLink"
        :href="project.link"
        target="_blank"
        class="project-link"
      >
        View API Documentation →
      </a>

      <!-- Coming Soon -->
      <span
        v-if="project.comingSoon"
        class="project-coming"
      >
        Coming Soon
      </span>
    </div>
  </div>
</template>

<script>
// ===============================
// UPDATED:
// Reusable grid-based project card
// Now supports:
// - Multiple links
// - Custom labels
// - Capstone support
// - NEW: tertiary & quaternary links
// ===============================

export default {
  props: {
    project: {
      type: Object,
      required: true
    }
  }
}
</script>