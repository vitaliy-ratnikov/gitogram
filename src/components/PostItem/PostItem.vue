<template>
  <div class="post-item">
    <div class="post-item-avatar">
      <img :src="avatar" alt="avatar" class="post-item-avatar__img">
      <p class="post-item-avatar__caption">{{ author }}</p>
    </div>
    <div class="post-item__topic">
      <slot name="topic"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: 'PostItem',
  props: {
    avatar: {
      type: String,
      required: true
    },
    author: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped lang="scss" src="./post-item.scss"></style>
