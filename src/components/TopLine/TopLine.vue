<template>
<div class="top-line">
  <div class="container">
    <div class="top-line-head">
      <slot name="headline" />
    </div>
    <div class="top-line__content top-line-content" v-if="$slots.content">
      <slot name="content"/>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'TopLine'
}
</script>

<style scoped lang="scss" src="./top-line.scss">

</style>
