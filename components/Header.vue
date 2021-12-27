<template>
  <div class="Header">
    <v-app-bar fixed dark collapse>
      <v-menu left bottom>
        <template v-slot:activator="{ on, attrs }">
          <v-btn icon v-bind="attrs" v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="n in 5" v-bind:key="n" @click="() => {}" :to="n === 1 ? '/' :'practica'+n" nuxt>
            <v-list-item-title>Efecto {{ n }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss" scoped>
</style>