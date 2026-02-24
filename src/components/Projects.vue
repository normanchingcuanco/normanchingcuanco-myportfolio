<template>
  <!-- =========================================================
       PROJECTS SECTION (MATCHES index.html VERSION)
       Now uses reusable <ProjectCard />
       UPDATED:
       - Added Live + GitHub links
       - Updated Allure project
       - Preserved ALL original projects
       - Short Courses now real projects
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
           UPDATED: Now uses real capstone data
      ========================================================== -->

      <div class="short-course-section mt-5">
        <h3 class="text-center mb-4 section-subtitle">
          Short Courses Capstone
        </h3>

        <div class="row justify-content-center g-4">

          <div
            class="col-12 col-md-6 col-lg-4"
            v-for="course in shortCourses"
            :key="course.title"
          >
            <ProjectCard :project="course" />
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
  PROJECT DATA (ALL ORIGINAL PROJECTS PRESERVED)
  Updated:
  - Project 1 → Added GitHub
  - Project 4 → Replaced Coming Soon with Live + GitHub
  =========================================================
*/
const projects = [
  {
    title: "E-commerce API Documentation",
    image: "/images/project1-ecommerce-api.png",
    description:
      "A dynamic e-commerce workflow management system featuring RESTful routes for order processing, real-time inventory updates, and secure user authentication. Supports automated order reporting, comprehensive product management, and a publicly documented backend API using Postman.",
    primaryLink: "https://documenter.getpostman.com/view/50806062/2sBXc7M4q6",
    primaryLabel: "View API Documentation →",
    secondaryLink: "https://github.com/normanchingcuanco/capstone2_ecommerce_api",
    secondaryLabel: "View GitHub Repository →"
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
    title: "Allure – Dating Marketplace Platform",
    image: "/images/project4-ecommerce.png",
    description:
      "Full-stack MERN marketplace platform connecting Filipinos with global users. Features authentication, profile management, transactional logic, service listings, and admin dashboard controls.",
    primaryLink: "https://allure-eta.vercel.app/",
    primaryLabel: "View Live Application →",
    secondaryLink: "https://github.com/normanchingcuanco/allure",
    secondaryLabel: "View GitHub Repository →"
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
  SHORT COURSES DATA (UPDATED WITH REAL CAPSTONES)
  =========================================================
*/
const shortCourses = [
  {
    title: "Capstone 1 – HTML/CSS Portfolio",
    image: "/images/online-learning.png",
    description:
      "Responsive developer portfolio built purely with HTML5 and CSS3. Focused on responsive layouts, semantic structure, and clean UI presentation.",
    primaryLink: "https://capstone1-chingcuanco-portfolio.vercel.app/",
    primaryLabel: "View Live Site →",
    secondaryLink: "https://github.com/normanchingcuanco/capstone1_chingcuanco_portfolio",
    secondaryLabel: "View GitHub →"
  },
  {
    title: "Capstone 1 – VueJS Portfolio Version",
    image: "/images/education.png",
    description:
      "Modern Vue 3 implementation of the developer portfolio using reusable components, reactive data structures, and structured project rendering.",
    secondaryLink: "https://github.com/normanchingcuanco/capstone1-vuejs",
    secondaryLabel: "View GitHub →"
  },
  {
    title: "Capstone 2 – E-commerce Backend API",
    image: "/images/graduation.png",
    description:
      "Backend API built with Node.js, Express.js, and MongoDB. Implements authentication, authorization, product management, and order processing.",
    secondaryLink: "https://github.com/normanchingcuanco/capstone2_ecommerce_api",
    secondaryLabel: "View GitHub →"
  },
  {
    title: "Capstone 3 – Allure Marketplace App",
    image: "/images/project4-ecommerce.png",
    description:
      "Full-stack MERN marketplace application with authentication, admin dashboard, service listing system, and transactional workflow deployed on Vercel.",
    primaryLink: "https://allure-eta.vercel.app/",
    primaryLabel: "View Live App →",
    secondaryLink: "https://github.com/normanchingcuanco/allure",
    secondaryLabel: "View GitHub →"
  }
]
</script>