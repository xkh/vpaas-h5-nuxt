<template>
  <div class="container">
    aaaa{{name}}
    <div v-for="(img, i) in images" :key="i">
      <img :src="img.src.default"/>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default{
    async asyncData({$axios}:any) {
     const { data } = await $axios.get(`http://127.0.0.1:7004/paas`)
     console.log('ddddd.....', JSON.stringify(data))
     const {fields} = data;
    return fields;
   }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
}
</style>
