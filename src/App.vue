<template>
  <div id="app">

    <div class="leftDiv">
      <label>perspective {{this.perspective}}px</label>
      <input type="range" min="0" max="180" v-model="perspective"/>
      <br/>
      <label> RotateX : {{this.RotateX}}deg</label>
      <input type="range" max="180" min="-180" v-model="RotateX"/>
      <br/>
      <label> RotateY : {{this.RotateY}}deg</label>
      <input type="range" max="180" min="-180" v-model="RotateY"/>
      <br/>
      <label>RotateZ : {{this.RotateZ}}deg</label>
      <input type="range" mix="180" min="-180" v-model="RotateZ"/>
    </div>
    <div class="rightDiv" :style="box">

    </div>

  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      perspective:100,
      RotateX:0,
      RotateY:0,
      RotateZ:0

    }
  },
  computed:{
    box(){
      return{
        transform :`
        perspective(${this.perspective}px)
        RotateX(${this.RotateX}deg)
        RotateY(${this.RotateY}deg)
        RotateZ(${this.RotateZ}deg)

        `
      }
    }
  }

}
</script>

<style>
body{
  background: #261c33;
}
#app {
  display: grid;
  grid-template-columns: 20% 20%;
  place-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}

.leftDiv {
  width: 200px;
  height: 200px;
  color: white;

}

.rightDiv {
  width: 200px;
  height: 200px;
  background: mediumpurple;
}
</style>
