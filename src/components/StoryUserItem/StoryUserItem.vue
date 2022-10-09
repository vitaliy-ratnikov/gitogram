<template>
  <button class="story-user-item" @click="$emit('onPress')">
    <div class="story-user-item-avatar">
      <img :src="avatar" alt="username avatar">
    </div>
    <p class="story-user-item__name">{{ username }}</p>
  </button>
</template>

<script>
export default {
  name: 'StoryUserItem',
  props: {
    avatar: {
      type: String,
      required: true
    },
    username: {
      type: String,
      required: true
    }
  }

}
</script>

<style scoped lang="scss" src="./story-user-item.scss"></style>
