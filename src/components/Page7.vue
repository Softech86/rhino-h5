<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
    <defs>

      <g id="background_7">
        <image xlink:href="static/6/1.png" width="90" height="160" />
      </g>
      <g id="rhino">

        <image xlink:href="static/6/2.png" x="5" width="90" height="160">
          <animate id="rhino-right" attributeName="x" values="3; 0" begin="rhino_show.end" dur=".5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
        </image>


        <image xlink:href="static/6/5.png" y="50" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" values="0; 1" begin="1.6s" dur=".3s" fill="freeze"/>
          <animate attributeName="y" values="50; 0" begin="1.5s" dur=".5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
        </image>


        <image xlink:href="static/6/6.png" x="0" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="2.7s" dur=".5s" fill="freeze"/>
        </image>

        <image xlink:href="static/6/7.png" x="0" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="2.5s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="1" to="0" begin="3.1s" dur=".5s" fill="freeze"/>
        </image>

        <image xlink:href="static/6/8.png" x="0" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="4.4s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="1" to="0" begin="5s" dur=".5s" fill="freeze"/>
        </image>

        <image xlink:href="static/6/9.png" x="0" width="90" height="160" style="opacity: 0">
          <animate ref="last"  attributeName="opacity" from="0" to="1" begin="4.6s" dur=".8s" fill="freeze"/>
        </image>

      </g>
      <g id="fire">

        <image xlink:href="static/6/3.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" values="0; 1; .3; 0; 0" begin="rhino_show.end + .3s" dur="2s" fill="freeze" repeatCount="2"/>
        </image>
        <image xlink:href="static/6/4.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" values="0; 1; .3; 0; 0" begin="rhino_show.end + 1.3s" dur="2s" fill="freeze" repeatCount="2"/>
        </image>
        <!--<image xlink:href="static/6/4.png" width="90" height="160" style="opacity: 0">-->
          <!--<animate attributeName="opacity" from="0" to="1" begin="rhino_show.end + .1s" dur=".1s" fill="freeze"/>-->
          <!--&lt;!&ndash;<animate attributeName="x" values="-20; 0" begin="rhino_show.end" dur="1.5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>&ndash;&gt;-->
          <!--&lt;!&ndash;<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>&ndash;&gt;-->
        <!--</image>-->

      </g>
      <g id="text7">
        <text font-size="5" y="36" x="29" style="opacity: 0">
          安全意识出色
          <animate attributeName="y" from="36" to="33" begin="1.5s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur=".3s" fill="freeze"/>

        </text>

      </g>
    </defs>

    <use xlink:href="#background_7" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate id="rhino_show" attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#text7" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
    <use xlink:href="#fire" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
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
      setTimeout(this.$refs.last.onend, 5500)
    }
  }
</script>

<style>
  text {
    letter-spacing: .02em;
  }
</style>


