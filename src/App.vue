<template>
  <MenuComponent/>
  <hr/>
  <router-view></router-view>
</template>

<script>
import MenuComponent from './components/Menu.vue'

export default {
  name: 'App',
  components: {
    MenuComponent
  },
}
</script>

<style>
</style>
