<template>
<div>
  <v-carousel hide-controls>
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>
    <nuxt-link to="/table"><center><h1>รายการ</h1></center></nuxt-link><br> 
    </div>
</template>
<script>
  export default {
    data () {
      return {
        items: [
          {
            src: '/image/Kudsan.png'
          },
          {
            src: '/image/sld1.jpg'
          },
          {
            src: '/image/Pastry.jpg'
          },
          {
            src: '/image/cafes.jpg'
          }
        ]
      }
    }
  }
</script>