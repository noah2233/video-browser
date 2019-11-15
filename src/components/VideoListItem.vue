
<template>
  <div>
    <li class="list-group-item">{{video.snippet.title}}</li>
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
