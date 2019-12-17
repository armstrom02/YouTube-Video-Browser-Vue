<template>
  <ul class="list-unstyled col-md-4">
    <VideoListItem
      v-for="video in videos"
      :video="video"
      :key="video.videoId"
      @videoSelect="onvideoSelect"
    >
    </VideoListItem>
  </ul>
</template>

<script>
import VideoListItem from "../components/VideoListItem";
export default {
  name: "VideoList",
  props: ["videos"],
  components: { VideoListItem },
  methods: {
    onvideoSelect(video) {
      this.$emit('videoSelect',video);
    }
  }
};
</script>

<style></style>
