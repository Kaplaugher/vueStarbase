<template>
  <div id="app">
    <h3>{{title}}</h3>
    <div class="col-md-12">
      <app-character :id="id" v-for="(id, index) in initial_ids"></app-character>
    </div>
  </div>

</template>

<script>
  import Character from './components/Character.vue';
export default {
  name: 'app',
  data () {
    return {
      title: 'Generate Your Team!',
      initial_ids: [1, 13, 14]
    }
  },
  methods: {
    fetchCharacter() {
      fetch('http://swapi.co/api/people/1', {
        method: 'GET'
      }).then(response => response.json())
        .then(json => console.log(json))
    }
  },
  components: {
    appCharacter: Character
  }
}
</script>

<style>

</style>
