<template>
  <button :class="['toggler-btn', {'toggler-btn--active': isOpened}]" @click="toggle">
    <span class="toggler-btn__text">
  {{ isOpened ? 'Hide' : 'Show' }} issues
</span>
    <span class="toggler-btn__icon">
    <base-icon name="ChevronIcon"/>
  </span>
  </button>
</template>

<script>
import BaseIcon from '@/icons/BaseIcon'

export default {
  name: 'TogglerBtn',
  components: { BaseIcon },
  data () {
    return {
      isOpened: false
    }
  },
  methods: {
    toggle () {
      this.isOpened = !this.isOpened
      this.$emit('onToggle', this.isOpened)
    }
  }
}
</script>

<style scoped lang="scss" src="./toggler-btn.scss">

</style>
