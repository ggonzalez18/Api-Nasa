<template>
  <div class="home">
    <v-img height="100vh" :src="image.url">
      <login></login>
    </v-img>
  </div>
</template>

<script>
// @ is an alias to /src
import Login from '@/components/Login.vue'
import { mapActions, mapState} from 'vuex'

export default {
  name: 'Home',
  components: {
    Login
  },
  methods: {
    ...mapActions(['setApod'])
  },
  computed: {
    ...mapState(['image'])
  },
  created() {
    this.setApod()
  }
}
</script>
