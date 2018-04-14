<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
    <defs>

      <g id="background_10">
        <image xlink:href="static/8/1.png" width="90" height="160" />
      </g>
      <g id="rhino">

        <image xlink:href="static/8/2.png" width="90" height="160" style="transform-origin: 5% 70%">
          <animateTransform attributeName="transform" type="scale" begin="1.2s" dur="4s" values="1; .9; .7; .7; .7; .7" fill="freeze" additive="sum"/>
        </image>
      </g>
      <g id="bullet">

        <image xlink:href="static/8/5.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur=".1s" fill="freeze"/>
          <animate attributeName="y" values="-20; 0" begin="1.5s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <animate attributeName="x" values="40; 0" begin="1.5s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>-->
        </image>
        <image xlink:href="static/8/4.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="1.9s" dur=".1s" fill="freeze"/>
          <animate attributeName="y" values="-20; 0" begin="1.9s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <animate attributeName="x" values="40; 0" begin="1.9s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>-->
        </image>
        <image xlink:href="static/8/3.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="2.3s" dur=".1s" fill="freeze"/>
          <animate attributeName="y" values="-20; 0" begin="2.3s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <animate  ref="last" attributeName="x" values="40; 0" begin="2.3s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>-->
        </image>

      </g>
      <g id="text10">
        <text font-size="5" y="33" x="19" style="opacity: 0">
          但即使是这样的我
          <animate attributeName="y" from="33" to="30" begin="1s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin="1s" dur=".3s" fill="freeze"/>

        </text>
        <text font-size="5" y="41" x="19" style="opacity: 0">
          也遭追杀
          <animate attributeName="y" from="41" to="38" begin="1.9s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin="1.9s" dur=".3s" fill="freeze"/>
        </text>

      </g>
    </defs>

    <use xlink:href="#background_10" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate id="rhino_show" attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#text10" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
    <use xlink:href="#bullet" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
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
      setTimeout(this.$refs.last.onend, 3500)
    }
  }
</script>

<style>
  text {
    letter-spacing: .02em;
  }
</style>


