<template>
  <!-- TOOLS SECTION -->
  <section id="tools" class="py-5">
    <div class="container">
      <h2 class="text-center mb-5">Tools</h2>

      <div class="row g-5">

        <!-- FRONT END -->
        <div
          class="col-12 col-md-4 text-center"
          v-for="category in tools"
          :key="category.name"
        >
          <h4 class="mb-4">{{ category.name }}</h4>

          <div class="row g-3 justify-content-center">

            <div
              class="col-6"
              v-for="tool in category.items"
              :key="tool.name"
            >
              <img
                :src="tool.image"
                :alt="tool.name"
                class="img-fluid tool-icon"
                :class="{ invert: tool.invert }"
              >
              <p class="mt-2">{{ tool.name }}</p>
            </div>

          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
const tools = [
  {
    name: "Front End",
    items: [
      { name: "HTML", image: "/images/html.png" },
      { name: "CSS", image: "/images/css-3.png" },
      { name: "Bootstrap", image: "/images/bootstrap.png" },
      { name: "JavaScript", image: "/images/js.png" }
    ]
  },
  {
    name: "MERN Stack",
    items: [
      { name: "MongoDB", image: "/images/mongodb.png", invert: true },
      { name: "Node.js", image: "/images/nodejs.png" },
      { name: "React", image: "/images/react.png" },
      { name: "Express", image: "/images/express-js.png", invert: true }
    ]
  },
  {
    name: "Other Tools",
    items: [
      { name: "Git", image: "/images/git.png" },
      { name: "Sublime", image: "/images/sublimetext.png" },
      { name: "Heroku", image: "/images/heroku.png" },
      { name: "Postman", image: "/images/postman.png" }
    ]
  }
]
</script>