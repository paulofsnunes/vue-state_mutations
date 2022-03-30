<template>
  <div id="app">
    {{$store.state.user}}
    <user-view/>
    <curso-view/>
  </div>
</template>

<script>

import UserView from '@/components/UserView.vue'
import CursoView from '@/components/CursoView.vue'

export default {
  name: 'App',
  components: {
    UserView,
    CursoView,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
