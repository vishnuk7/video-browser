<template>
  <ul>{{ videos.length }}</ul>
</template>

<script>
export default {
  name: "VideoList",
  props: ["videos"]
};
</script>