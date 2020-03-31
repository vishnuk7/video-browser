<template>
  <li class="list-group-item media d-flex" @click="onSelectedVideo">
    <img class="mr-3" :src="thumbnails" />
    <div class="media-body">
      <h5 class="mt-0 mb-1">{{ video.snippet.title }}</h5>
    </div>
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    thumbnails() {
      return this.video.snippet.thumbnails.default.url;
    }
  },
  methods: {
    onSelectedVideo() {
      this.$emit("video", this.video);
    }
  }
};
</script>

<style scoped>
li {
  transition: all 0.2s;
}
li:hover {
  background-color: #eee;
}
</style>