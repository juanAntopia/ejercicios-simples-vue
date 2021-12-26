<template>
  <v-sheet color="#034071">
    <div class="Practica2">
      <v-container fluid>
        <v-row style="min-height: 100vh" align="center" justify="center">
          <v-col cols="auto">
            <div class="runway"></div>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </v-sheet>
</template>

<script>
export default {
  name: "Practice2",
};
</script>

<style lang="scss" scoped>
.runway{
    position: relative;
    width: 400px;
    max-width: 100%;
    height: 100vh;
    background: #1378bc;
}
</style>