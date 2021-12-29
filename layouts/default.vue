<template>
  <v-app>
      <v-main>
          <Intro></Intro>
          <Header v-if="!intro"></Header>
          <nuxt v-if="!intro"></nuxt>
      </v-main>
  </v-app>
</template>

<script>
export default {
    name: "App",
    data () {
        return {
            intro: true
        }
    },
    mounted () {
      this.$nuxt.$on('closeIntro', ()=>{
          this.intro = false
      })
        
    }
}
</script>

<style>

</style>