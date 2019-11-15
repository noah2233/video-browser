
<template>
  <div>
    <li class="list-group-item">
      <img class="mr-3" :src="thumbnailUrl" />
      <div class="media-body">{{video.snippet.title}}</div>
    </li>
  </div>
</template>

<script>
export default {
  name: "VideoListItem",
  props: {
    video: Object
  },
  computed: {
    thumbnailUrl() {
      return this.video.snippet.thumbnails.default.url;
    }
  }
};
</script>
<style scoped>
li {
  display: flex;
  cursor: pointer;
}
li:hover {
  background-color: #eee;
}
</style>
