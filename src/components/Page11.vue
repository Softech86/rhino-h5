<template>
  <svg id="svg" width="100%" height="100%" viewBox="0,0,90,160">
    <defs>

      <g id="background_11">
        <image xlink:href="static/9/1.png" width="90" height="160" />
      </g>
      <g id="rhino">

        <image xlink:href="static/9/2.png" width="90" height="160">
          <!--<animate id="rhino-right" attributeName="x" values="0; 6" begin="rhino_show.end + .8s" dur="1s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>-->
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

      <g id="btn1">
        <rect width="28" height="12.5" x="-2" rx="1" ry="1" style="fill:white;stroke-width:.2;stroke:rgb(0,0,0)" />
        <text x="1.5" y="8" font-size="5">
          持续关注
        </text>
      </g>

      <g id="btn2">
        <rect width="28" height="12.5" x="30" rx="1" ry="1" style="fill:white;stroke-width:.2;stroke:rgb(0,0,0);opacity: 0">
          <animate attributeName="opacity" from="0" to="1" begin="2.2s" dur=".5s" fill="freeze"/>
        </rect>
        <text x="33.5" y="8" font-size="5" style="opacity: 0">
          合力保护
          <animate attributeName="opacity" from="0" to="1" begin="2.2s" dur=".5s" fill="freeze"/>
        </text>
      </g>

      <g id="text11">
        <text font-size="5" y="38" x="18" style="opacity: 0">
          我需要你的保护和关注
          <animate attributeName="y" from="38" to="34" begin=".8s" dur=".5s" fill="freeze"/>
          <animate attributeName="opacity" from="0" to="1" begin=".8s" dur=".3s" fill="freeze"/>
        </text>

      </g>
    </defs>

    <use xlink:href="#background_11" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
      <animate attributeName="y" from="0" to="-15" begin=".5s" dur="1.5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
    </use>
    <use xlink:href="#rhino" x="0" y="0" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate id="rhino_show" attributeName="opacity" from="0" to="1" begin=".3s" dur=".5s" fill="freeze"/>
      <animate attributeName="y" from="0" to="-15" begin=".5s" dur="1.5s" calcMode="spline" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
    </use>
    <use xlink:href="#text11" x="0" y="0" preserveAspectRatio="xMinYMin meet" />
    <use xlink:href="#btn1" x="17" y="140" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="y" from="140" to="135" begin="1.6s" dur=".8s" calcMode="spline" keyTimes="0; 1" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
      <animate attributeName="opacity" from="0" to="1" begin="1.6s" dur=".8s" fill="freeze"/>
    </use>
    <use xlink:href="#btn2" x="17" y="140" preserveAspectRatio="xMinYMin meet" style="opacity: 0">
      <animate attributeName="y" from="140" to="135" begin="2s" dur=".8s" calcMode="spline" keyTimes="0; 1" keySplines="0.45, 0.05, 0.55, 0.95" fill="freeze"/>
      <animate attributeName="opacity" from="0" to="1" begin="1.7s" dur=".8s" fill="freeze"/>
    </use>
  </svg>
</template>

<style>
  text {
    letter-spacing: .02em;
  }
</style>


