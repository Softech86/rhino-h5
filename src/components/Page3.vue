<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
      <!-- <text font-family="microsoft yahei" font-size="120" y="160" x="160">马
          <animate attributeName="x" from="160" to="60" begin="0s" dur="3s" repeatCount="indefinite" />
          <animate attributeName="opacity" from="1" to="0" begin="0s" dur="3s" repeatCount="indefinite" />
      </text>
      <image xlink:href="Penguins.jpg" x="000" y="0" height="50px" width="50px"/>
      <rect x="10" y="5" width="400" height="15" fill="#cd0000"/> -->
      <!-- <defs>
        <g id="rhino-umbrella">
          <image xlink:href="static/1/3.png" width="90" height="160" />
          <image xlink:href="static/1/7.png" width="90" height="160" />
        </g>
        <g id="ripple">
          <image :xlink:href="`static/1/${name}.png`" width="90" height="160" y="3" style="opacity: 0" v-for="(name, i) in [6, 4, 5]" :key="i">
            <animate attributeName="opacity" :begin="1.9 + 2.5 / 3 * i + 's'" dur="2.5s" keyTimes="0; .25; .5; 1" values="0; 1; 0; 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95; 0,0,1,1" repeatCount="indefinite"/>
          </image>
        </g>
        <g id="city">
          <image xlink:href="static/1/1.png" width="90" height="160" style="opacity: 0">
            <animate attributeName="opacity" begin=".8s" dur="1.2s" values="0; 1" fill="freeze"/>
          </image>
        </g>
      </defs>

      <use xlink:href="#city" x="0" y="0" preserveAspectRatio="xMinYMin meet"/>
      <use xlink:href="#ripple" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 1" />
      <use xlink:href="#rhino-umbrella" x="0" y="-160" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
        <animate id="down" attributeName="y" dur="2.5s" values="-160; 0;" keyTimes="0; 1" calcMode="spline" keySplines="0.39, 0.58, 0.57, 1" fill="freeze"/>
        <animate attributeName="y" begin="down.end" dur="2.5s" values="0; -2; 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95" repeatCount="indefinite"/>
        <animate attributeName="opacity" begin=".3s" dur=".5s" values="0; 1" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
      </use> -->

      <defs>
        <g id="background_3">
          <!--<image xlink:href="static/2/6.png" width="90" height="160" />-->
          <image xlink:href="static/2/7.png" width="90" height="160" x="-90" style="opacity: 0">
            <animate attributeName="x" values="-90; 0" begin="2.8s" dur=".9s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
            <animate attributeName="opacity" from="0" to=".8" begin="2.8s" dur=".3s" fill="freeze"/>
          </image>
        </g>
        <g id="rhino-e">
          <image xlink:href="static/2/4.png" width="90" height="160" />
          <image xlink:href="static/2/5.png" width="90" height="160" />
        </g>
        <g id="text3">
          <text font-size="5" y="34" x="48" style="opacity: 0">
            我眼睛不好
              <animate id="text3_1" attributeName="y" from="34" to="32" begin="1.5s" dur=".5s" fill="freeze"/>
              <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur=".3s" fill="freeze"/>
          </text>

          <text font-size="4" y="85" x="16" style="opacity: 0">
            视力 0.2
              <animate attributeName="y" from="85" to="84" begin="text3_1.end" dur=".5s" fill="freeze"/>
              <animate attributeName="opacity" from="0" to=".8" begin="text3_1.end" dur=".3s" fill="freeze"/>
          </text>

          <text font-size="5" y="34" x="-42" style="opacity: 0">
            但是心地善良
              <animate attributeName="opacity" from="0" to="1" begin="4s" dur=".5s" fill="freeze"/>
          </text>
        </g>
        <g id="rhinos">
          <image :xlink:href="`static/2/${name}.png`" width="90" height="160" y="3" style="opacity: 0" v-for="(name, i) in [2, 1, 3, 1]" :key="i">
            <animate attributeName="opacity" :begin="1.9 + 2.5 / 4 * i + 's'" dur="2.5s" keyTimes="0; .2; .4; 1" values="0; 1; 0; 0" calcMode="spline" keySplines="0, 0, 0, 1; 1,0,1, 1; 0,0,1,1" repeatCount="indefinite"/>
          </image>
        </g>
        <!-- <g id="btn">
          <rect width="56" height="12" rx="1" ry="1" style="fill:white;stroke-width:.2;stroke:rgb(0,0,0)" />
          <text x="8" y="8"  font-size="5">
            点我，了解一下？
          </text>
        </g> -->
      </defs>

      <use xlink:href="#background_3" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
        <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
      </use>
      <use xlink:href="#rhino-e" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
        <animate attributeName="y" from="10" to="0" begin=".5s" dur="1s"/>
        <animate attributeName="opacity" from="0" to="1" begin=".5s" dur=".5s" fill="freeze"/>
        <animate attributeName="x" values="0; 90" begin="2.8s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
      </use>
      <use xlink:href="#text3" x="0" y="0" preserveAspectRatio="xMinYMin meet">
        <animate attributeName="x" values="0; 90" begin="2.8s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
      </use>
      <use xlink:href="#rhinos" x="-90" y="0" preserveAspectRatio="xMinYMin meet">
        <animate attributeName="x" ref="last"  values="-90; 0" begin="2.8s" dur="5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
      </use>
  </svg>
</template>

<script>
  export default {
    mounted () {
      for (var i = 4; i <= 6; ++ i) {
        for (var j = 1; j <= [7, 7, 11, 8, 4, 9, 6, 5, 2][i - 1]; ++j) {
          (document.createElement('img')).setAttribute('src', '/static/' + i + '/' + j + '.png')
        }
      }

      const t = new Date()
      this.$refs.last.onend = this.$refs.last.onended = () => {
        this.$emit('done')
        console.log(new Date() - t)
      }
      setTimeout(this.$refs.last.onend, 8000)
    }
  }
</script>

<style>
  text {
    letter-spacing: .03em;
  }
</style>


