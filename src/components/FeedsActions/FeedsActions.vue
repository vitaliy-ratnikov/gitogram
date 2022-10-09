<template>
  <div class="feeds-actions">
    <div class="feeds-actions__wrap feeds-actions-wrap">
      <button class="feeds-actions-wrap__btn feeds-actions-wrap-btn">
        <base-icon name="StarIcon" class="feeds-actions-wrap-btn__icon"/>
        <span class="feeds-actions-wrap-btn__caption">Star</span>
      </button>
      <p class="feeds-actions-wrap__info">{{ starInfo }}</p>
    </div>
    <div class="feeds-actions__wrap feeds-actions-wrap">
      <button class="feeds-actions-wrap__btn feeds-actions-wrap-btn">
        <base-icon name="ForkIcon" class="feeds-actions-wrap-btn__icon"/>
        <span class="feeds-actions-wrap-btn__caption">Fork</span>
      </button>
      <p class="feeds-actions-wrap__info">{{ forkInfo }}</p>

    </div>
  </div>
</template>

<script>
import BaseIcon from '@/icons/BaseIcon'

export default {
  name: 'FeedsAction',
  components: { BaseIcon },
  props: {
    starInfo: {
      type: String,
      required: false
    },
    forkInfo: {
      type: String,
      required: false
    }
  }
}
</script>

<style scoped lang="scss" src="./feeds-actions.scss"></style>
