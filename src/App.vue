<template>
  <div id="app" class="container">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <div class="row">
      <VideoDetail :video="video"></VideoDetail>
      <VideoList :videos="videos" @video="onSelectedVideo"></VideoList>
    </div>
  </div>
</template>

<script>
import axios from "axios";

import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";

const API_KEY = process.env.VUE_APP_API_KEY;

export default {
  name: "App",
  data() {
    return {
      videos: [],
      video: null
    };
  },
  components: {
    SearchBar,
    VideoList,
    VideoDetail
  },
  methods: {
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(res => {
          this.videos = res.data.items;
          this.video = res.data.items[0];
        });
    },
    onSelectedVideo(video) {
      console.log(video);
      this.video = video;
    }
  }
};
</script>

<style></style>
