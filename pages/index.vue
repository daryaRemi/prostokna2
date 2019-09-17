<template>
  <section>
    <h1 class="title">
      USERS
    </h1>
    <nuxt-link to="/contact">contact</nuxt-link><br>
    <nuxt-link to="/test">test</nuxt-link>
    <ul class="users">
      <li v-for="(user, index) in users" :key="index" class="user">
        <nuxt-link :to="{ name: 'id', params: { id: index }}">
          {{ user.name }}
        </nuxt-link>
      </li>
    </ul>
    <LeftMenu></LeftMenu>
    <div>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Excepturi, ipsum, minima ullam incidunt pariatur expedita dolorem explicabo hic optio vero sint quo, iste architecto voluptates doloribus quaerat? Dolor, harum accusantium.</div>
    <Footer></Footer>
  </section>
</template>

<script>
import axios from '~/plugins/axios'
import LeftMenu from '~/components/LeftMenu/component.vue'
import Footer from '~/components/Footer/component.vue'

export default {
  components: {
    LeftMenu,
    Footer
  },
  async asyncData () {
    let { data } = await axios.get('/api/users')
    return { users: data }
  },
  head () {
    return {
      title: 'Users'
    }
  }
}
</script>
