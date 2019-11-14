
<template>
  <div>
    <li>{{video.snippet.title}}</li>
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
