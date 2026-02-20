<template>
  <!-- =========================================================
       PROJECTS SECTION (MATCHES index.html VERSION)
       Now uses reusable <ProjectCard />
  ========================================================== -->
  <section id="projects" class="py-5">
    <div class="container">

      <h2 class="text-center mb-5 section-title">My Projects</h2>

      <div class="row g-4">

        <!-- PROJECT CARDS -->
        <div
          class="col-12 col-md-6 col-lg-4"
          v-for="project in projects"
          :key="project.title"
        >
          <ProjectCard :project="project" />
        </div>

      </div>

      <!-- =========================================================
           SHORT COURSES CAPSTONE (SAME CARD SYSTEM)
      ========================================================== -->

      <div class="short-course-section">
        <h3 class="text-center mb-4 section-subtitle">
          Short Courses Capstone
        </h3>

        <div class="row justify-content-center g-4">

          <div
            class="col-12 col-md-6 col-lg-4"
            v-for="course in shortCourses"
            :key="course.image"
          >
            <div class="project-card short-course-card">
              <div class="project-img-wrapper short-course-img">
                <img :src="course.image" alt="Short Courses">
              </div>
              <div class="project-body text-center">
                <h6>Short Courses Project</h6>
                <p class="project-desc mb-0">
                  Placeholder for your Short Courses capstone project.
                </p>
              </div>
            </div>
          </div>

        </div>
      </div>

    </div>
  </section>
</template>

<script setup>
/*
  =========================================================
  IMPORT COMPONENT
  =========================================================
*/
import ProjectCard from "@/components/ProjectCard.vue"

/*
  =========================================================
  PROJECT DATA (MATCHES index.html EXACTLY)
  =========================================================
*/
const projects = [
  {
    title: "E-commerce API Documentation",
    image: "/images/project1-ecommerce-api.png",
    link: "https://documenter.getpostman.com/view/50806062/2sBXc7M4q6",
    description:
      "A dynamic e-commerce workflow management system featuring RESTful routes for order processing, real-time inventory updates, and secure user authentication. Supports automated order reporting, comprehensive product management, and a publicly documented backend API using Postman.",
    comingSoon: false
  },
  {
    title: "Course Booking API Documentation",
    image: "/images/project2-course-api.png",
    description:
      "RESTful API for managing course enrollments, featuring user registration, authentication, and retrieval of user details. Supports course creation, updates, archiving, activation, and student enrollment. Publicly documented using Postman.",
    comingSoon: true
  },
  {
    title: "Course Booking App",
    image: "/images/project3-course.png",
    description:
      "MERN stack course enrollment system featuring user registration, authentication, and profile management. Authenticated users can manage courses while students browse and enroll seamlessly.",
    comingSoon: true
  },
  {
    title: "E-commerce App",
    image: "/images/project4-ecommerce.png",
    description:
      "MERN e-commerce platform featuring a dynamic product catalog, real-time search, secure checkout, and an admin dashboard with analytics and user management.",
    comingSoon: true
  },
  {
    title: "Airline Booking System Mockup",
    image: "/images/project5-airline-booking.png",
    description:
      "Side project showcasing an intuitive UI for flight search, seat selection, and booking confirmation.",
    comingSoon: true
  },
  {
    title: "Airline Booking System Prototype",
    image: "/images/project6-airline-prototype.png",
    description:
      "Interactive prototype simulating end-to-end airline booking including reservations, payments, and ticket management.",
    comingSoon: true
  }
]

/*
  =========================================================
  SHORT COURSES DATA
  =========================================================
*/
const shortCourses = [
  { image: "/images/online-learning.png" },
  { image: "/images/graduation.png" },
  { image: "/images/education.png" }
]
</script>