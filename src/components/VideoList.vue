<template>
  <ul>
    <VideoListItem 
    v-for="video in videos" 
    :video="video"  
    :key="video.videoId">
    </VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from "../components/VideoListItem";
export default {
  name: "VideoList",
  props: ["videos"],
  components: { VideoListItem }
};
</script>

<style></style>
