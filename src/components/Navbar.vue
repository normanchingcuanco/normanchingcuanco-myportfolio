<template>
  <!-- NAVBAR -->
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark fixed-top premium-navbar">
    <div class="container">
      <a class="navbar-brand premium-brand" href="#landing">MyPortfolio</a>

      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navlinks"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="navlinks">
        <ul class="navbar-nav ms-auto premium-navlinks">
          <li class="nav-item"><a class="nav-link" href="#landing">Home</a></li>
          <li class="nav-item"><a class="nav-link" href="#projects">My Projects</a></li>
          <li class="nav-item"><a class="nav-link" href="#tools">Tools</a></li>
          <li class="nav-item"><a class="nav-link" href="#contact">Contact</a></li>
        </ul>

        <!-- ===============================
             NEW NOTE (NAV CLEANUP):
             Removed redundant “Let’s Talk” CTA.
        ================================ -->
      </div>
    </div>
  </nav>
</template>