<template>
    <header>
      <!-- Fixed navbar -->
      <nav class="navbar navbar-expand-md navbar-dark fixed-top bg-primary">
        <div class="container">
          <a class="navbar-brand fs-1" href="#">ShowFlix</a>
          <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarCollapse"
            aria-controls="navbarCollapse"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarCollapse">
            <ul class="navbar-nav ms-auto mb-2 mb-md-0 align-items-center">
              <li class="nav-item">
                <a class="nav-link active fs-5" href="#">Log in</a>
              </li>
              <li class="nav-item">
                <button class="btn btn-secondary btn-lg" type="button">
                  Start your free trial
                </button>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </header>
</template>