<template>
  <!-- =========================================================
       SINGLE PROJECT CARD (UPDATED VERSION)
       Now supports:
       - Multiple links (Live + GitHub)
       - Custom button labels
       - Works for Short Courses + Projects
       - Backward compatible with old structure
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

      <!-- =====================================================
           PRIMARY LINK (Live / Documentation)
           NEW: supports dynamic label
      ====================================================== -->
      <a
        v-if="project.primaryLink"
        :href="project.primaryLink"
        target="_blank"
        class="project-link"
      >
        {{ project.primaryLabel || "View Project →" }}
      </a>

      <!-- =====================================================
           SECONDARY LINK (GitHub Repo)
           NEW: allows GitHub link display
      ====================================================== -->
      <a
        v-if="project.secondaryLink"
        :href="project.secondaryLink"
        target="_blank"
        class="project-link"
      >
        {{ project.secondaryLabel || "View GitHub →" }}
      </a>

      <!-- =====================================================
           BACKWARD COMPATIBILITY (OLD link PROPERTY)
      ====================================================== -->
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