<template>
  <div class="container">
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoDetail :video="selectedVideo"></VideoDetail>
    <VideoList :videos="videos" @videoSelect="onVideoSelect"></VideoList>
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";

const API_KEY = "AIzaSyBeaVjeakVaXF-yzRDMc7tL_-d_rv_f-wA";

export default {
  name: "App",
  components: {
    SearchBar: SearchBar,
    VideoList: VideoList,
    VideoDetail: VideoDetail
  },
  data() {
    return { videos: [], selectedVideo: null };
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
    },
    onVideoSelect(video) {
      this.selectedVideo = video;
    }
  }
};
</script>
