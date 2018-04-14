<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
    <defs>

      <g id="background_6">
        <image xlink:href="static/5/1.png" width="90" height="160" />
      </g>
      <g id="rhino">

        <image xlink:href="static/5/2.png" width="90" height="160">
          <animate  ref="last" id="rhino-right" attributeName="x" values="0; 6" begin="rhino_show.end + .8s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
        </image>
        <!--<image xlink:href="static/4/6.png" width="90" height="160" style="opacity: 0">-->
          <!--<animate id="rhino_dirty" attributeName="opacity" from="0" to="1" begin="bucket_drop.end" dur=".3s" fill="freeze"/>-->
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_dirty.end + 1s" dur=".3s" fill="freeze"/>-->
        <!--</image>-->
        <!--<image xlink:href="static/4/8.png" width="90" height="160" style="opacity: 0">-->
          <!--<animate attributeName="opacity" from="0" to="1" begin="rhino_dirty.end + .5s" dur=".3s" fill="freeze"/>-->
          <!--&lt;!&ndash;<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>&ndash;&gt;-->
        <!--</image>-->

        <!--<image xlink:href="static/4/4.png" width="90" height="160" >-->
          <!--<animate attributeName="y" from="0" to="5" begin="bucket_drop.end" dur=".2s"  calcMode="spline" keyTimes="0; 1" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>-->
        <!--</image>-->
      </g>
      <g id="goose">

        <image xlink:href="static/5/3.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="rhino_show.end + .1s" dur=".1s" fill="freeze"/>
          <animate attributeName="x" values="20; 0" begin="rhino_show.end" dur="1.5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>-->
        </image>
        <image xlink:href="static/5/4.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="rhino_show.end + .1s" dur=".1s" fill="freeze"/>
          <animate attributeName="x" values="-20; 0" begin="rhino_show.end" dur="1.5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>-->
        </image>

      </g>
      <g id="text6">
        <text font-size="5" y="36" x="29" style="opacity: 0">
          社交能力爆表
          <animate attributeName="y" from="36" to="33" begin="1.5s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur=".3s" fill="freeze"/>

        </text>

      </g>
    </defs>

    <use xlink:href="#background_6" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate id="rhino_show" attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#text6" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
    <use xlink:href="#goose" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
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
      setTimeout(this.$refs.last.onend, 2600)
    }
  }
</script>

<style>
  text {
    letter-spacing: .02em;
  }
</style>


