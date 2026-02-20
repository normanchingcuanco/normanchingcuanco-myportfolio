<template>
  <!-- SINGLE PROJECT CARD -->
  <div
    class="row align-items-center mb-4"
    :class="{ 'flex-md-row-reverse': project.reverse }"
  >
    <div class="col-12 col-md-6">
      <img
        :src="project.image"
        class="img-fluid rounded mb-3 mb-md-0"
        :alt="project.title"
      >
    </div>

    <div class="col-12 col-md-6">
      <h5>{{ project.title }}</h5>

      <a v-if="project.link" :href="project.link" target="_blank">
        View API Documentation
      </a>

      <p>{{ project.description }}</p>

      <span v-if="!project.link" class="text-muted">Coming Soon</span>
    </div>
  </div>
</template>

<script>
// ===============================
// NEW:
// Reusable dynamic project card
// ===============================

export default {
  props: {
    project: Object
  }
}
</script>