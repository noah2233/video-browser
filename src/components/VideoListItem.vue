
<template>
  <div>
    <li class="list-group-item">
      <img :src="video.snippet.thumbnails.default.url" />
      {{video.snippet.title}}
    </li>
  </div>
</template>

<script>
export default {
  name: "VideoListItem",
  props: {
    video: Object
  }
};
</script>
