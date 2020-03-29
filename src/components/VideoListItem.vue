<template>
  <li>
    <img :src="thumbnails" />
    {{ video.snippet.title }}
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
  }
};
</script>