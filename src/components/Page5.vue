<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
    <defs>

      <g id="background_5">
        <image xlink:href="static/4/1.png" width="90" height="160" />
      </g>
      <g id="rhino">
        <image xlink:href="static/4/3.png" width="90" height="160" >
          <animate attributeName="y" from="0" to="5" begin="bucket_drop.end" dur=".2s"  calcMode="spline" keyTimes="0; 1" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>
        </image>

        <image xlink:href="static/4/2.png" width="90" height="160">
          <animate attributeName="opacity" from="1" to="0" begin="bucket_drop.end" dur=".3s" fill="freeze"/>
        </image>
        <image xlink:href="static/4/6.png" width="90" height="160" style="opacity: 0">
          <animate id="rhino_dirty" attributeName="opacity" from="0" to="1" begin="bucket_drop.end" dur=".3s" fill="freeze"/>
          <animate attributeName="opacity" from="1" to="0" begin="rhino_dirty.end + 1s" dur=".3s" fill="freeze"/>
        </image>
        <image xlink:href="static/4/8.png" width="90" height="160" style="opacity: 0">
          <animate  ref="last"  attributeName="opacity" from="0" to="1" begin="rhino_dirty.end + .5s" dur=".3s" fill="freeze"/>
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>-->
        </image>

        <image xlink:href="static/4/4.png" width="90" height="160" >
          <animate attributeName="y" from="0" to="5" begin="bucket_drop.end" dur=".2s"  calcMode="spline" keyTimes="0; 1" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>
        </image>
      </g>
      <g id="bucket">
        <image xlink:href="static/4/5.png" y=-100 width="90" height="160" style="opacity: 0">
          <!--<animate id="text3_1" attributeName="y" from="-90" to="0" begin="rhino_show.end" dur=".5s" fill="freeze"/>-->
          <animate id="bucket_drop" attributeName="y" from="-100" to="0" begin="rhino_show.end + .3s" dur=".7s" calcMode="spline" keyTimes="0; 1" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="1" to="0" begin="bucket_drop.end" dur=".3s" fill="freeze"/>
        </image>
        <image xlink:href="static/4/7.png" width="90" height="160" style="opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="bucket_drop.end + .1s" dur=".1s" fill="freeze"/>
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>-->
        </image>

      </g>
      <g id="text5">
        <text font-size="5" y="36" x="21" style="opacity: 0">
          玩泥巴是上海滩一霸
          <animate attributeName="y" from="36" to="33" begin="1.5s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur=".3s" fill="freeze"/>

          <!--<animate id="text3_1" attributeName="y" from="120" to="115" begin="rhino_out.end + .3s" dur=".5s" fill="freeze"/>-->
          <!--<animate attributeName="opacity" from="1" to="0" begin="rhino_out.end + .3s" dur=".3s" fill="freeze"/>-->
        </text>

      </g>
    </defs>

    <use xlink:href="#background_5" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#bucket" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
    <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate id="rhino_show" attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
    </use>
    <use xlink:href="#text5" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
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


