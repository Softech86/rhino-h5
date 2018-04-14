<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
      <defs>

        <g id="background_4">
          <image xlink:href="static/3/9.png" width="90" height="160" />
        </g>
        <g id="rhino">
          <image xlink:href="static/3/2.png" width="90" height="160">
            <animate attributeName="opacity" from="1" to="0" begin="rhino_shake.end" dur=".3s" fill="freeze"/>
          </image>
          <image xlink:href="static/3/3.png" width="90" height="160" style="opacity: 0">
            <animate attributeName="opacity" from="0" to="1" begin="rhino_shake.end" dur=".3s" fill="freeze"/>
            <animate attributeName="opacity" from="1" to="0" begin="rhino_scared.end" dur=".3s" fill="freeze"/>
          </image>

          <image xlink:href="static/3/1.png" width="90" height="160" style="opacity: 0">
            <animate attributeName="opacity" from="0" to="1" begin="rhino_scared.end" dur=".3s" fill="freeze"/>
            <animate attributeName="opacity" from="1" to="0" begin="rhino_out.end" dur=".3s" fill="freeze"/>
          </image>
          <image xlink:href="static/3/10.png" width="90" height="160" style="opacity: 0 ; transform-origin: 30% 50%">
            <animate attributeName="opacity" from="0" to="1" begin="rhino_scared.end" dur=".3s" fill="freeze"/>
            <animate attributeName="opacity" from="1" to="0" begin="rhino_out.end" dur=".3s" fill="freeze"/>
            <animateTransform attributeName="transform" type="rotate" begin="rhino_scared.end + .2s" dur=".3s" values="3 0 0;-3 0 0;3 0 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95" fill="freeze" repeatCount="indefinite" additive="sum"/>
          </image>


          <image xlink:href="static/3/7.png" width="90" height="160" style="opacity: 0">
            <animate attributeName="opacity" from="0" to="1" begin="rhino_out.end" dur=".3s" fill="freeze"/>
            <animate attributeName="opacity" from="1" to="0" begin="rhino_scared_running.end + .4s" dur=".3s" fill="freeze"/>
          </image>
          <image xlink:href="static/3/11.png" width="90" height="160" style="opacity: 0 ; transform-origin: 50% 50%">
            <animate attributeName="opacity" from="0" to="1" begin="rhino_out.end" dur=".3s" fill="freeze"/>
            <animate attributeName="opacity" from="1" to="0" begin="rhino_scared_running.end + .4s" dur=".3s" fill="freeze"/>
            <animateTransform attributeName="transform" type="rotate" begin="rhino_scared.end + .2s" dur=".3s" values="3 0 0;-3 0 0;3 0 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95" fill="freeze" repeatCount="indefinite" additive="sum"/>
          </image>

          <image xlink:href="static/3/8.png" width="90" height="160" style="opacity: 0">
            <animate  ref="last" attributeName="opacity" from="0" to="1" begin="rhino_scared_running.end + .6s" dur=".3s" fill="freeze"/>
          </image>

          <image xlink:href="static/3/6.png" width="90" height="160" x=0 y=0 style="opacity: 0">
            <animate attributeName="opacity" from="0" to="1" begin="rhino_scared_running.end" dur=".3s" fill="freeze"/>
          </image>

        </g>

        <g id="box">
          <image xlink:href="static/3/4.png" width="90" height="160" />
          <image xlink:href="static/3/5.png" width="90" height="160" style="transform-origin: 72% 50%;">
            <animateTransform attributeName="transform" type="scale" begin="0" end="rhino_shake.end" values="0; 0" accumulate="sum"/>
            <animateTransform attributeName="transform" type="scale" begin="rhino_shake.end" dur=".5s" values="0; 1" calcMode="spline" keySplines="0.22, 0.61, 0.36, 1" fill="freeze" additive="sum"/>
            <animateTransform attributeName="transform" type="rotate" begin="rhino_shake.end" dur=".5s" values="10 0 0;-10 0 0;10 0 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95" fill="freeze" repeatCount="indefinite" additive="sum"/>
            <!-- <animateTransform attributeName="transform" type="scale" from="1" to="3" dur="10s" repeatCount="indefinite" additive="sum"/> -->
          </image>

        </g>

        <g id="text4">
          <text font-size="5" y="135" x="18" style="opacity: 0">
            我有梁静茹给的勇气
            <animate id="text3_1" attributeName="y" from="135" to="130" begin="1.5s" dur=".5s" fill="freeze"/>
            <animate attributeName="opacity" from="0" to="1" begin="1.5s" dur=".3s" fill="freeze"/>

            <animate id="text3_1" attributeName="y" from="130" to="125" begin="rhino_out.end + .3s" dur=".5s" fill="freeze"/>
            <animate attributeName="opacity" from="1" to="0" begin="rhino_out.end + .3s" dur=".3s" fill="freeze"/>
          </text>

          <text font-size="5" y="40" x="23" style="opacity: 0">
            也有五月天给的温柔
            <animate id="text3_1" attributeName="y" from="45" to="40" begin="rhino_scared_running.end" dur=".5s" fill="freeze"/>
            <animate attributeName="opacity" from="0" to="1" begin="rhino_scared_running.end" dur=".3s" fill="freeze"/>

            <!-- <animate id="text3_1" attributeName="y" from="120" to="115" begin="rhino_out.end" dur=".5s" fill="freeze"/>
            <animate attributeName="opacity" from="1" to="0" begin="rhino_out.end" dur=".3s" fill="freeze"/> -->
          </text>
        </g>
      </defs>

      <use xlink:href="#background_4" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
        <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
      </use>

      <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0; transform-origin: 30% 50%">
        <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".3s" fill="freeze"/>
        <!-- <animateTransform attributeName="transform" type="rotate" from="0 30 20" to="360 30 20" dur="10s" fill="freeze" repeatCount="indefinite"/>; -->
        <animateTransform id="rhino_shake" attributeName="transform" begin="0s" dur="2s" type="rotate" values="-1 0 0;1 0 0;-1 0 0;5 0 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95; 0.45, 0.05, 0.55, 0.95" fill="freeze"/>
        <animateTransform attributeName="transform" begin="rhino_shake.end + .1s" dur=".3s" type="rotate" values="5 0 0;-5 0 0" calcMode="spline" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>
        <animateTransform id="rhino_scared" attributeName="transform" begin="rhino_shake.end + .4s" dur=".3s" type="rotate" values="-5 0 0;-3 0 0;-5 0 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95;0.45, 0.05, 0.55, 0.95"/>
        <animateTransform id="rhino_scared_running" attributeName="transform" begin="rhino_scared.end" dur=".3s" type="rotate" values="-5 0 0;-3 0 0;-5 0 0" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95;0.45, 0.05, 0.55, 0.95" repeatCount="8"  fill="freeze"/>

        <animate id="rhino_out" attributeName="x" begin="rhino_shake.end + .8s" dur="1s" type="translate" values="0;80" calcMode="spline" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>
        <animate attributeName="x" begin="rhino_out.end" dur="1s" type="translate" values="80; 0" calcMode="spline" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>
        <!-- <animateTransform attributeName="transform" begin="rhino_out.end" dur="2s" type="rotate" values="0 0 0;0 0 180" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" addictive="sum"/> -->

      </use>
      <use xlink:href="#box" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
        <animate attributeName="opacity" from="0" to="1" begin=".8s" dur=".3s" fill="freeze"/>
        <animate attributeName="y" from="-12" to="0" begin=".8s" dur=".3s" calcMode="spline" keyTimes="0; 1" keySplines="0.47, 0, 0.75, 0.72" fill="freeze"/>

        <animate attributeName="x" from="0" to="40" begin="rhino_scared.end + .3s" dur=".6s" calcMode="spline" keyTimes="0; 1" keySplines="0, 0, 1, 1" fill="freeze"/>
        <animate attributeName="y" from="0" to="-120" begin="rhino_scared.end + .3s" dur=".8s" calcMode="spline" keyTimes="0; 1" keySplines="0, .2, 0.4, 1" fill="freeze"/>
      </use>

      <use xlink:href="#text4" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
  </svg>
</template>

<script>
  export default {
    mounted () {
      for (var i = 7; i <= 9; ++ i) {
        for (var j = 1; j <= [7, 7, 11, 8, 4, 9, 6, 5, 2][i - 1]; ++j) {
          (document.createElement('img')).setAttribute('src', '/static/' + i + '/' + j + '.png')
        }
      }

      const t = new Date()
      this.$refs.last.onend = this.$refs.last.onended = () => {
        this.$emit('done')
        console.log(new Date() - t)
      }
      setTimeout(this.$refs.last.onend, 6000)
    }
  }
</script>

<style>
  text {
    letter-spacing: .02em;
  }
</style>


