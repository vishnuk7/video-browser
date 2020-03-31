<template>
  <ul class="list-group list-unstyled col-md-4">
    <VideoListItem
      v-for="video in videos"
      :video="video"
      :key="video.etag"
      @video="onSelectedVideo"
    ></VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from "./VideoListItem";

export default {
  name: "VideoList",
  props: ["videos"],
  components: {
    VideoListItem
  },
  methods: {
    onSelectedVideo(video) {
      this.$emit("video", video);
    }
  }
};
</script>