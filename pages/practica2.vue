<template>
  <v-sheet color="#034071">
    <div class="Practica2">
      <v-container fluid>
        <v-row style="min-height: 100vh" align="center" justify="center">
          <v-col cols="auto" class="pa-0" id="Fly">
            <div class="runway"></div>
            <img
              :src="require('@/assets/img/plane.png')"
              alt=""
              srcset=""
              class="plane"
            />
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
.plane {
  position: absolute;
  bottom: 100px;
  max-width: 250px;
  left: 50%;
  transform: translate(-50%);
  pointer-events: none;
  filter: drop-shadow(10px 10px 0 rgba(0, 0, 0, 0.5));
  transition: 5s;
}
#Fly {
  .runway {
    position: relative;
    width: 400px;
    max-width: 100%;
    min-height: 100vh;
    background: #1378bc;
    border-left: 20px solid rgba(0, 0, 0, 0.25);
    border-right: 20px solid rgba(0, 0, 0, 0.25);
    transition: transform 1s;
    transition-delay: 1s;
    transform-origin: top;

    &::before {
      content: "";
      position: absolute;
      width: 10px;
      height: 100%;
      left: 50%;
      transform: translateX(-50%);
      background: repeating-linear-gradient(
        transparent 0%,
        transparent 50%,
        #fff 50%,
        #fff 100%
      );
      background-size: 20px 320px;
      animation: animationRunway 1s linear infinite;
    }
  }
  &:active {
    .runway {
      &::before {
        animation: animationRunway 0.25s linear infinite;
      }
      transform: scaleX(0.7) scaleY(0);
      transition-delay: 0s;
      transform-origin: bottom;
    }

    .plane {
      max-width: 500px;
      filter: drop-shadow(200px 200px 0 rgba(0, 0, 0, 0.5));
    }
  }
}

@keyframes animationRunway {
  0% {
    background-position-y: 0px;
  }
  100% {
    background-position-y: 620px;
  }
}
</style>