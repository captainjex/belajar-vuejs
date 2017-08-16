<template>
 <div id="app">
   <h3>Starbase Router hehehe</h3>
   <h4>
      <router-link class="link" to="/data/people">Meet the Character</router-link> |
      <router-link class="link" to="/data/planets">Explore the Planet</router-link>
   </h4>
   <router-view></router-view>
 </div>
</template>

<script>
export default {
}
</script>
