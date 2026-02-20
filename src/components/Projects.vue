<template>
  <!-- PROJECTS SECTION -->
  <section id="projects" class="py-5">
    <div class="container">

      <h2 class="text-center mb-5">My Projects</h2>

      <!-- ===============================
           NEW LAYOUT NOTE:
           Converted to modern grid layout.
      ================================ -->

      <div class="row g-4">

        <div class="col-12 col-md-6" v-for="project in projects" :key="project.title">
          <div class="project-card">
            <div class="project-img-wrapper">
              <img :src="project.image" :alt="project.title">
            </div>
            <div class="project-body">
              <h5>{{ project.title }}</h5>
              <a v-if="project.link" :href="project.link" target="_blank">View API Documentation</a>
              <p>{{ project.description }}</p>
              <span v-if="project.comingSoon" class="text-muted">Coming Soon</span>
            </div>
          </div>
        </div>

      </div>

      <!-- SHORT COURSES -->
      <div class="short-course-section">
        <h3 class="text-center mb-4">Short Courses Capstone</h3>
        <div class="row justify-content-center g-4">
          <div class="col-12 col-md-4 text-center">
            <img src="/images/online-learning.png" class="img-fluid mb-2">
            <p>Placeholder for your Short Courses capstone project.</p>
          </div>
          <div class="col-12 col-md-4 text-center">
            <img src="/images/graduation.png" class="img-fluid mb-2">
            <p>Placeholder for your Short Courses capstone project.</p>
          </div>
          <div class="col-12 col-md-4 text-center">
            <img src="/images/education.png" class="img-fluid mb-2">
            <p>Placeholder for your Short Courses capstone project.</p>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: "E-commerce API Documentation",
    image: "/images/project1-ecommerce-api.png",
    link: "https://documenter.getpostman.com/view/50806062/2sBXc7M4q6",
    description: "RESTful routes for order processing and authentication.",
    comingSoon: false
  },
  {
    title: "Course Booking API Documentation",
    image: "/images/project2-course-api.png",
    description: "API for managing enrollments and authentication.",
    comingSoon: true
  },
  {
    title: "Course Booking App",
    image: "/images/project3-course.png",
    description: "MERN stack enrollment system.",
    comingSoon: true
  },
  {
    title: "E-commerce App",
    image: "/images/project4-ecommerce.png",
    description: "MERN e-commerce platform.",
    comingSoon: true
  },
  {
    title: "Airline Booking System Mockup",
    image: "/images/project5-airline-booking.png",
    description: "UI for flight booking.",
    comingSoon: true
  },
  {
    title: "Airline Booking System Prototype",
    image: "/images/project6-airline-prototype.png",
    description: "Interactive reservation system.",
    comingSoon: true
  }
]
</script>