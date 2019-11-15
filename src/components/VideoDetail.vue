<template>
  <div>{{ video?video.snippet.title:null }}</div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"]
};
</script>

<style scoped>
</style>