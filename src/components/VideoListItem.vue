
<template>
  <div>
    <li class="list-group-item">
      <img :src="thumbnailUrl" />
      {{video.snippet.title}}
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
