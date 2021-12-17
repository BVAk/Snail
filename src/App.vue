<template>
  <div class="connections">
    <canvas id="pixi"></canvas>
  </div>
</template>

<script>
import * as PIXI from 'pixi.js'
window.PIXI = PIXI;

export default {
  name: 'App',
  methods: {
    drawPixi() {
      var canvas = document.getElementById('pixi')

      const app = new PIXI.Application({
        width: window.innerWidth,
        height: window.innerHeight,
        antialias: true,
        backgroundAlpha: true,
        view: canvas,
      })

      let graphics = new PIXI.Graphics() 
      graphics.lineStyle(8, 0x000000)

      //start
      graphics.moveTo(300, 250)
      //end
      graphics.lineTo(500, 250)

      app.stage.addChild(graphics)
    },
  },

  mounted() {
    this.drawPixi()
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
