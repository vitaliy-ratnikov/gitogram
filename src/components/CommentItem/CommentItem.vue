<template>
    <p class="comment-item">
      <span class="comment-item__user">{{ username }}</span>
      {{ text }}
    </p>
</template>

<script>
export default {
  name: 'CommentItem',
  props: {
    username: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped lang="scss" src="./comment-item.scss">

</style>
