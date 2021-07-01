<template>
  <div class="app-main-layout">
    <nav-bar @click="isOpen = !isOpen" />
    <side-bar :isOpen="isOpen"/>
    <main class="app-content" :class="{full: !isOpen}">
      <div class="app-page">
        <router-view/>
      </div>
    </main>

    <div class="fixed-action-btn">
      <router-link class="btn-floating btn-large blue" to="/record" active-class="hidden">
        <i class="large material-icons">add</i>
      </router-link>
    </div>
  </div>
</template>

<script>
import NavBar from '@/components/app/NavBar.vue'
import SideBar from '@/components/app/SideBar.vue'
export default {
  name: 'main-layout',
  data: () => ({
    isOpen: true
  }),
  components: {
    NavBar, SideBar
  }
}
</script>

<style lang="scss">
.hidden{
  display: none;
}
</style>
