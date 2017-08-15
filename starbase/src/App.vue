<template>
<div id="app">
  <h3>{{ title }}</h3>
  <div class="row">
    <div class="col-md-12">
      <Character
        v-for="(id, index) in initial_ids"
        :id="id"
        key="index"
      />
    </div>
  </div>
</div>
</template>

<script>
import Character from './components/Character.vue'

export default {
  name: 'app',
  data() {
    return {
      title: 'Generate your team asd',
      initial_ids: [1, 3, 14]
    }
  },
  components: {
    Character
  }
}
</script>
