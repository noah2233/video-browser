<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList></VideoList>
    {{ videos.length }}
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";

import VideoList from "./components/VideoList";

const API_KEY = "AIzaSyBeaVjeakVaXF-yzRDMc7tL_-d_rv_f-wA";

export default {
  name: "App",
  components: {
    SearchBar: SearchBar,
    VideoList: VideoList
  },
  data() {
    return { videos: [] };
  },
  methods: {
    onTermChange: function(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(response => {
          this.videos = response.data.items;
        });
    }
  }
};
</script>