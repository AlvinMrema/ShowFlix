<template>
  <div class="d-flex flex-column h-100">
    <TheHeader />

    <main class="flex-shrink-0">
      <div class="my-5 py-1 bg-secondary">
        <section class="container">
          <div class="d-flex justify-content-between mt-5">
            <h2 class="fs-4 text-white">
              Popular
              {{ showHome ? "Titles" : showMovies ? "Movies" : "Series" }}
            </h2>
            <button
              v-if="!showHome"
              @click="showView()"
              class="btn btn-primary mb-2"
            >
              Back Home
            </button>
          </div>
        </section>
      </div>

      <section class="my-5">
        <div class="container">
          <div v-show="showHome" class="row">
            <HomePage :categories="categories" @category-clicked="showView" />
          </div>

          <div v-show="showMovies" class="row">
            <MoviesPage :moviesList="moviesList" />
          </div>

          <div v-show="showSeries" class="row">
            <SeriesPage :seriesList="seriesList" />
          </div>
        </div>
      </section>
    </main>

    <TheFooter />
  </div>
</template>

<script>
import sample from "./feed/sample.json";
import TheHeader from "@/components/TheHeader.vue";
import TheFooter from "@/components/TheFooter.vue";
import SeriesPage from "@/pages/SeriesPage.vue";
import MoviesPage from "@/pages/MoviesPage.vue";
import HomePage from "@/pages/HomePage.vue"

export default {
  name: "App",
  components: { TheHeader, TheFooter, SeriesPage, MoviesPage, HomePage },
  data() {
    return {
      contentData: sample,
      categories: ["movies", "series"],
      showMovies: false,
      showSeries: false,
      showHome: true,
    };
  },
  computed: {
    moviesList() {
      return this.contentData.entries.filter(
        (data) => data.programType === "movie"
      );
    },
    seriesList() {
      return this.contentData.entries.filter(
        (data) => data.programType === "series"
      );
    },
  },
  methods: {
    showView(name = "Title") {
      if (name === "movies") {
        this.showMovies = true;
        this.showSeries = false;
        this.showHome = false;
      } else if (name === "series") {
        this.showSeries = true;
        this.showMovies = false;
        this.showHome = false;
      } else {
        this.showHome = true;
        this.showMovies = false;
        this.showSeries = false;
      }
    },
  },
};
</script>
