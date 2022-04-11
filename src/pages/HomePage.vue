<template>
  <div class="col-sm-4" v-for="category in categories" :key="category">
    <div class="card m-2">
      <img
        src="./../assets/placeholder.png"
        class="card-img-top bg-dark"
        :alt="category"
      />
      <div class="card-body">
        <h5 class="card-title">{{ category.toUpperCase() }}</h5>
        <p class="card-text">
          Popular {{ category[0].toUpperCase() + category.slice(1) }}
        </p>
        <button @click="$emit('category-clicked', category)" class="btn btn-primary">
          Check List
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  emits: ['category-clicked'],
  props: {
    categories: Array,
  }
};
</script>