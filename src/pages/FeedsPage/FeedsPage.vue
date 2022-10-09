<template>
  <div class="feeds-page">
    <top-line>
      <template #headline>
        <main-logo/>
        <top-menu-control/>
      </template>

      <template #content>
        <ul class="feeds-page-stories">
          <li v-for="story in storyUsers" :key="story.id">
            <story-user-item
              :username="story.username"
              :avatar="story.avatar"
              @onPress="handlePress(story.id)"
            />
          </li>
        </ul>
      </template>
    </top-line>
    <ul class="feeds-page__list feeds-page-list">
      <li class="feeds-page-list__item" v-for="post in posts" :key="post.id">
        <post-item :avatar="post.avatar" :author="post.username">
          <template #topic>
            <div class="feeds-page-list-topic">
              <h2 class="feeds-page-list-topic__title">
                {{ post.title }}
              </h2>
              <p
                class="feeds-page-list-topic__description"
                v-html="post.description"></p>
              <feeds-action
                :forkInfo="post.forkInfo"
                :starInfo="post.starInfo"
                class="feeds-page-list-topic__action"
              />
            </div>
          </template>
        </post-item>

        <feed-item class="feeds-page-list__issues"/>

        <p class="feeds-page-list__date">{{ post.date }}</p>
      </li>
    </ul>

  </div>
</template>

<script>
import TopLine from '@/components/TopLine/TopLine'
import StoryUserItem from '@/components/StoryUserItem/StoryUserItem'
import stories from './data.json'
import posts from './postData.json'
import storyUsers from './storyUsersData.json'
import PostItem from '@/components/PostItem/PostItem'
import FeedsAction from '@/components/FeedsActions/FeedsActions'
import FeedItem from '@/components/FeedItem/FeedItem'
import TopMenuControl from '@/components/TopMenuControl/MenuItem'
import MainLogo from '@/components/MainLogo/MainLogo'

export default {
  name: 'FeedsPage',
  components: {
    MainLogo,
    TopMenuControl,
    FeedItem,
    FeedsAction,
    PostItem,
    StoryUserItem,
    TopLine
  },
  data () {
    return {
      stories,
      posts,
      shown: false,
      storyUsers
    }
  },
  methods: {
    handlePress (evt) {
      console.log(evt)
    },
    toggle (isOpened) {
      this.shown = isOpened
    }
  }
}
</script>

<style scoped lang="scss" src="./feeds-page.scss"></style>
