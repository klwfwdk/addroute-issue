<template>
  <div class="home">
    <button @click="addrouter">replace with router named About</button>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  methods: {
    addrouter() {
      this.$router.addRoute(
        {
          path: '/about',
          name: 'About',
          // route level code-splitting
          // this generates a separate chunk (about.[hash].js) for this route
          // which is lazy-loaded when the route is visited.
          component: () => import(/* webpackChunkName: "about" */ '../views/AboutNew.vue')
        }
      )
    }
  }
}
</script>
