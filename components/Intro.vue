<template>
  <v-dialog fullscreen v-model="intro" transition="fade-transition">
    <v-card elevation="0" tile color="black">
      <section class="video-section">
        <h2 class="white--text">Juan Developer</h2>
        <video
          :src="require('@/assets/videos/FumefxColoredSmoke.mp4')"
          autoplay
          loop
          muted
          type="video/mp4"
          playsinline
        ></video>
      </section>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "IntroAnimation",
  data() {
    return {
      intro: true,
    };
  },
  mounted() {
    setTimeout(() => {
      this.intro = false;
      this.$nuxt.$emit('closeIntro')
    }, 10000);
  },
};
</script>

<style lang="scss" scoped>
.video-section {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  width: 100%;

  h2 {
    font-size: 8em;
    z-index: 10000;
    mix-blend-mode: overlay;
  }

  video {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    pointer-events: none;
  }
}
</style>