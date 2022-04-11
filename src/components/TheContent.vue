<template>
  <div class="card mb-3">
    <div class="row g-0">
      <div class="col-md-4">
        <img
          :src="images['Poster Art'].url"
          class="img-fluid rounded-start align-self-stretch"
          :width="images['Poster Art'].width"
          :height="images['Poster Art'].height"
          alt="..."
        />
      </div>
      <div class="col-md-8">
        <div class="card-body">
          <h5 class="card-title">{{ title }}</h5>
          <p class="card-text">
            {{ description }}
          </p>
          <p class="card-text">
            <small class="text-muted"
              >Release Year: {{ releaseYear }}</small
            >
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'ContentItem',
    props: {
        title: String,
        images: Object,
        releaseYear: Number,
        description: String
    }
};
</script>