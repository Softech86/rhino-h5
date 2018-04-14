<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
    <defs>

      <g id="background_8">
        <image xlink:href="static/7/1.png" width="90" height="160" />
      </g>
      <g id="rhino">

        <image xlink:href="static/7/5.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" values="0; 1" begin=".5s" dur="1s" fill="freeze"/>
          <animate attributeName="opacity" values="1; 0" begin="3.6s" dur=".5s" fill="freeze"/>
        </image>

        <image xlink:href="static/7/6.png" width="90" height="160" style="opacity: 0; transform-origin: center 60%">
          <animate attributeName="opacity" values="0; 1" begin="2.4s" dur=".8s" fill="freeze"/>
          <animateTransform attributeName="transform" type="rotate" begin="4s" dur="1s" values="0 0 0;20 0 0" fill="freeze" repeatCount="indefinite" accumulate="sum"/>

          <!--<animate attributeName="opacity" values="1; 0" begin="6.2s" dur=".5s" fill="freeze"/>-->
        </image>

        <image xlink:href="static/7/4.png" y="50" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" values="0; 1" begin=".7s" dur=".5s" fill="freeze"/>
          <animate attributeName="y" values="-3; 0" begin=".7s" dur=".5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>


          <animate  ref="last" attributeName="opacity" values="1; 0" begin="2.5s" dur=".3s" fill="freeze"/>
        </image>
      </g>
    </defs>

    <use xlink:href="#background_8" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate id="rhino_show" attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
  </svg>
</template>

<script>
  export default {
    mounted () {
      const t = new Date()
      this.$refs.last.onend = this.$refs.last.onended = () => {
        this.$emit('done')
        console.log(new Date() - t)
      }
      setTimeout(this.$refs.last.onend, 5000)
    }
  }
</script>

<style>
  text {
    letter-spacing: .02em;
  }
</style>


