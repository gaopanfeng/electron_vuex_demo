<template>
  <div class="app">
    test
    <h1>Vuex Electron</h1>
    <h3>Example of usage</h3>

    <div class="count">
      {{count}}
    </div>

    <div class="buttons">
      <button v-on:click="increment">Increment</button>
      <button v-on:click="decrement">Decrement</button>
    </div>

    <p class="note">
      <small>Number automatically increments each 5 seconds<br>from main process</small>
    </p>
  </div>
</template>


<script>
  import { mapState, mapActions } from 'vuex'

  // In renderer process to call actions you need to use `dispatch` or `mapActions`
  // Don't use `commit` because actions fired via `commit` will not be shared between processes

  export default {
    computed: mapState(['count']),
    methods: mapActions(['increment', 'decrement'])
  }
</script>

<style type="scss">

</style>
