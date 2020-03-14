<template>
  <div>
    <!--
    {{ $route.params.species }}
    {{ $route.params.id }}
    -->
    <h1>{{ animal.name }}</h1>

    <p>Age: {{ animal.breed }} years old</p>
    <p>Breed: {{ animal.age }}</p>
  </div>
</template>

<script>
// import { mapState } from 'vuex'

export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    cats () {
      return this.$store.state.cats
    },
    dogs () {
      return this.$store.state.dogs
    }
    // ...mapState([
    //   'cats',
    //   'dogs'
    // ])
  },
  mounted () {
    this.animal = this[this.$route.params.species][this.$route.params.id]
  }
}
</script>
