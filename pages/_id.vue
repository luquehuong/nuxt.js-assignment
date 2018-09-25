<template>
  <div>
    detail
    {{ beer_id }}

  </div>
</template>

<script>
export default {
  asyncData(ctx) {
    return {
      beer_id: ctx.params.id
    }
  }
}
</script>

<style scoped>
</style>
