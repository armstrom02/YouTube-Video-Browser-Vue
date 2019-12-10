<template>
  <div>
    <SearchBar @termChange="onTermChange"></SearchBar>
    <VideoList></VideoList>
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
const API_KEY = "AIzaSyDMdvNTFrVfJaPZp1vAEKGZBWJvRaSM7C8";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList
  },
  data() {
    return {
       
    };
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
          console.log(res);
        });
    }
  }
};
</script>
