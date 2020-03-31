<template>
  <div v-if="video" :video="video" class="col-md-8">
    <div class="border rounded video-detail">
      <div class="embed-responsive embed-responsive-16by9">
        <iframe class="embed-responsive-item" :src="youtubeUrl" allowfullscreen></iframe>
      </div>
      <h4 class="text-dark">{{ video.snippet.title }}</h4>
      <p class="text-secondary">{{ video.snippet.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"],
  computed: {
    youtubeUrl() {
      const { videoId } = this.video.id;
      return `https://www.youtube.com/embed/${videoId}`;
    }
  }
};
</script>

<style scoped>
.video-detail {
  padding: 2rem 1rem;
}
</style>