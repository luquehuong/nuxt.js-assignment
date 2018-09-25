<template>
  <div>
    <div
      v-for="item in beers"
      :key="item.id"
    >
      <nuxt-link
        :to="`/${item.id}`" 
      >
        {{ item.name }}
      </nuxt-link>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      beers: []
    }
  },
  async created() {
    try {
      const { data } = await axios.get('https://api.punkapi.com/v2/beers')
      console.log(data)
      this.beers = data
    } catch (e) {
      console.log(e)
    }
  }
}
</script>

<style scoped>
</style>
