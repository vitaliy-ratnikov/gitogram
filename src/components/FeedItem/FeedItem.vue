<template>
  <div class="feed-item">
    <toggler-btn @onToggle="toggle"/>
    <div class="feed-item__comments" v-if="shown">
      <ul>
        <li v-for="comment in comments" :key="comment.id">
          <comment-item  :username="comment.author" :text="comment.message"/>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import TogglerBtn from '@/components/TogglerBtn/TogglerBtn'
import CommentItem from '@/components/CommentItem/CommentItem'
import comments from './commentsData.json'

export default {
  name: 'FeedItem',
  components: {
    CommentItem,
    TogglerBtn
  },
  data () {
    return {
      shown: false,
      comments
    }
  },
  methods: {
    toggle (isOpened) {
      this.shown = isOpened
    }
  }
}
</script>

<style scoped lang="scss" src="./feed-item.scss">

</style>
