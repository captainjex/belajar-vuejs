<template>
<div class="col-md-4" @click="switchCharacter">
  <div class="character-card">
    <div class="card-block">
      <h1 class="card-title">{{ character.name }}</h1>
      <p class="card-text">height: {{ character.height }}</p>
      <p class="card-text">mass: {{ character.mass }}kg</p>
      <p class="card-text">hair_color: {{ character.hair_color }}</p>
      <p class="card-text">eye_color: {{ character.eye_color }}</p>
    </div>
  </div>
</div>
</template>

<script>
export default {
  props: ['id'],
  data() {
    return {
      character: {}
    }
  },
  methods: {
    fetchCharacter(id) {
      fetch(`http://swapi.co/api/people/${id}`, {
        method: 'GET'
      })
        .then(response => response.json())
        .then(json => this.character = json)
    },
    switchCharacter() {
      let random_id = Math.floor(Math.random() * 83) + 1
      this.fetchCharacter(random_id)
    }
  },
  created() {
    this.fetchCharacter(this.id)
  }
}
</script>
