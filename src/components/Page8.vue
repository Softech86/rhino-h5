<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
    <defs>

      <g id="background_8">
        <image xlink:href="static/7/1.png" width="90" height="160" />
      </g>
      <g id="rhino">

        <image xlink:href="static/7/2.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" values="0; 1; .8; 0; 0" begin=".3s" dur="1.6s" fill="freeze" repeatCount="indefinite"/>
        </image>
        <image xlink:href="static/7/3.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" values="0; 1; .8; 0; 0" begin="1.1s" dur="1.6s" fill="freeze" repeatCount="indefinite"/>
        </image>

      </g>
      <!--<g id="goose">-->

        <!--<image xlink:href="static/5/3.png" width="90" height="160" style="opacity: 0">-->
          <!--<animate attributeName="opacity" from="0" to="1" begin="rhino_show.end + .1s" dur=".1s" fill="freeze"/>-->
          <!--<animate attributeName="x" values="20; 0" begin="rhino_show.end" dur="1.5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>-->
          <!--&lt;!&ndash;<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>&ndash;&gt;-->
        <!--</image>-->
        <!--<image xlink:href="static/5/4.png" width="90" height="160" style="opacity: 0">-->
          <!--<animate attributeName="opacity" from="0" to="1" begin="rhino_show.end + .1s" dur=".1s" fill="freeze"/>-->
          <!--<animate attributeName="x" values="-20; 0" begin="rhino_show.end" dur="1.5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>-->
          <!--&lt;!&ndash;<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>&ndash;&gt;-->
        <!--</image>-->

      <!--</g>-->
      <g id="text8">
        <text font-size="5" y="36" x="29" style="opacity: 0">
          减肥效果显著
          <animate ref="last"  attributeName="y" from="36" to="33" begin="2s" dur=".8s" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin="2s" dur=".8s" fill="freeze"/>

        </text>

      </g>
    </defs>

    <use xlink:href="#background_8" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate id="rhino_show" attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#text8" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
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
      setTimeout(this.$refs.last.onend, 3000)
    }
  }
</script>

<style>
  text {
    letter-spacing: .02em;
  }
</style>


