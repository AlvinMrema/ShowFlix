<template>
  <div class="col-lg-4" v-for="movie in moviesList.slice(0, 20)" :key="movie">
    <TheContent
      :title="movie.title"
      :releaseYear="movie.releaseYear"
      :images="movie.images"
      :description="movie.description"
    />
  </div>
</template>

<script>
import TheContent from "@/components/TheContent.vue";
export default {
  name: "MoviesPage",
  components: { TheContent },
  props: {
    moviesList: Array,
  },
};
</script>