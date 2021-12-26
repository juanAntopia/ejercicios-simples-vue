<template>
  <v-sheet color="#0e1538">
    <div class="Home">
       <v-container fluid>
         <v-row justify="center" align="center" style="min-height: 100vh">
           <v-col cols="auto">
             <div class="box"><h2>{{counter}}</h2></div>
           </v-col>
         </v-row>
       </v-container>
    </div>
  </v-sheet>
</template>

<script>
export default {
  name: "home",
  data () {
    return {
      counter: 0
    }
  },
  mounted () {
    setInterval(()=>{
      if(this.counter < 10) {
        this.counter++
      } else {
        this.counter = 0
      }
    }, 1000)
  }
}
</script>

<style lang="scss" scoped>
.Home{
  font-family: 'Times New Roman', Times, serif;
}

.box{
  position: relative;
  width: 300px;
  height: 400px;
  display: flex;
  justify-content: center;
  align-items: center;
  background: rgba(0,0,0,0.5);
  overflow: hidden;
  border-radius: 20px;

  h2{
    position: relative;
    color: white;
    font-size: 10em;
    z-index: 1;
  }

  &::before{
    content: "";
    position: absolute;
    width: 150px; 
    height: 140%;
    background: linear-gradient(#00ccff, #d400d4); 
    animation: animate 4s linear infinite;
  }

  &::after {
    content: "";
    position: absolute;
    inset: 4px;
    background: #0e1538;
    border-radius: 16px;
  }
}

@keyframes animate {
  0%{
    transform: rotate(0deg);
  }
  100%{
    transform: rotate(360deg);
  }
}

</style>