<template>
  <div class="col-lg-4" v-for="series in seriesList.slice(0, 20)" :key="series">
    <TheContent
      :title="series.title"
      :releaseYear="series.releaseYear"
      :images="series.images"
      :description="series.description"
    />
  </div>
</template>

<script>
import TheContent from "@/components/TheContent.vue";
export default {
  name: "SeriesPage",
  components: { TheContent },
  props: {
    seriesList: Array,
  },
};
</script>