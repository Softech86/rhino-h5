<template>
  <svg id="svg" width="100vw" height="100vh" viewBox="0,0,90,160">
    <defs>
      <g :id="id" v-for="(data, id) in defs" :key="id" v-html="parseDefs(data)">
        <image xlink:href="static/3/9.png" width="90" />
      </g>
    </defs>
  </svg>
</template>

<script>
export default {
  data () {
    return {
      defs: {
        rhino5: {
          url: 'static/3/3.png'
        }
      }
    }
  },
  methods: {
    parseDefs (data) {
      const images = []
      if (data instanceof Array) {
        images.push(...data)
      } else {
        images.push(data)
      }
      return JSON.stringify(images)      
    }
  }
}
</script>
