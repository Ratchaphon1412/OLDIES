<template>
  <div>
    <video ref="bangkok" autoplay loop muted playsinline>
      <source src="video/Bangkok.mp4" type="video/mp4" />
    </video>
  </div>
</template>

<script>
export default {
  name: 'VideoBangkok',
  mounted() {
    const video = this.$refs.bangkok
    video.playbackRate = 2
  },
}
</script>

<style scoped>
video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
