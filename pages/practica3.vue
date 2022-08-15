<template>
  <div class="libraryEfect">
    <!-- <p class="p1">Hello world</p>

    <div style="margin-top: 200px;">
      <button @click="p2">click me</button>
      <p class="p2" v-anime="{color: '#2f495e', backgroundColor: '#00c58e', loop: true, duration: 3000}">this is example</p>
    </div> -->

    <button @click="staggering" style="margin-top: 500px;">CLICK</button>
    <div class="basic-staggering-demo">
    <p class="el">ELEMENT</p>
    <p class="el">ELEMENT</p>
    <p class="el">ELEMENT</p>
  </div>
  </div>
</template>

<script>
export default {
  name: "Practica3",
  mounted () {
    // this.p1();
    // this.staggering();
  },
  methods: {
    p1: function () {
      const anime = this.$anime;

      anime({
        targets: '.p1',
        translateX: 250,
        rotate: '1turn',
        backgroundColor: "#fff",
        duration: 800
      })
    },
    p2: function () {
      this.$anime({
        targets: '.p2',
        translateX: 250,
        rotate: '1turn',
        backgroundColor: '#fff',
        duration: 800
    })
    },
    staggering() {
      const anime = this.$anime
      anime({
        targets: '.basic-staggering-demo .el',
        translateX: 270,
        delay: anime.stagger(100) // increase delay by 100ms for each elements.
      })
    }
  }
}
</script>

<style>

</style>