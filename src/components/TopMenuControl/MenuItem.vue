<template>
  <ul class="top-menu-control">
    <li v-for="menuListItem in menuListItems" :key="menuListItem.id">
      <a :href="menuListItem.href" class="top-menu-control__link">
        <template v-if="menuListItem.id === 'Profile'">
          <img :src="`/img/${menuListItem.img}`" :alt="menuListItem.img" class="top-menu-control__img">
        </template>
        <template v-else>
          <base-icon :name="menuListItem.id" class="top-menu-control__icon base-icon"/>
        </template>
      </a>

    </li>
  </ul>
</template>

<script>
import BaseIcon from '@/icons/BaseIcon'

export default {
  name: 'TopMenuControl',
  components: { BaseIcon },
  data () {
    return {
      menuListItems: [
        {
          id: 'HomeIcon',
          href: '/'
        },
        {
          id: 'Profile',
          href: '/profile',
          img: 'Profile.png'
        },
        {
          id: 'SignOutIcon',
          href: '/sign-out'
        }

      ]
    }
  }
}
</script>

<style scoped lang="scss" src="./top-menu-control.scss"></style>
