<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
      <!-- <text font-family="microsoft yahei" font-size="120" y="160" x="160">马
          <animate attributeName="x" from="160" to="60" begin="0s" dur="3s" repeatCount="indefinite" />
          <animate attributeName="opacity" from="1" to="0" begin="0s" dur="3s" repeatCount="indefinite" />
      </text>
      <image xlink:href="Penguins.jpg" x="000" y="0" height="50px" width="50px"/>
      <rect x="10" y="5" width="400" height="15" fill="#cd0000"/> -->
      <defs>
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
        <animate id="down" ref="last" attributeName="y" dur="2.5s" values="-160; 0;" keyTimes="0; 1" calcMode="spline" keySplines="0.39, 0.58, 0.57, 1" fill="freeze"/>
        <animate attributeName="y" begin="down.end" dur="2.5s" values="0; -2; 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95" repeatCount="indefinite"/>
        <animate attributeName="opacity" begin=".3s" dur=".5s" values="0; 1" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
      </use>
  </svg>
</template>

<script>
  export default {
    mounted () {
      window.last = this.$refs.last
      const t = new Date()
      const f = () => {
        this.$emit('done')
        console.log(new Date() - t)
      }
      this.$refs.last.onend = this.$refs.last.onWebkitAnimationEnd = this.$refs.last.WebkitAnimationEnd = this.$refs.last.onended = f
      setTimeout(f, 3000)
    }
  }
</script>
