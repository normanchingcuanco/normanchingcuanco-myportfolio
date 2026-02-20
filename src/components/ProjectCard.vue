<template>
  <!-- =========================================================
       SINGLE PROJECT CARD (NEW GRID VERSION)
       Matches index.html + Projects.vue layout
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

      <!-- Link -->
      <a
        v-if="project.link"
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
// Matches new portfolio design system
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