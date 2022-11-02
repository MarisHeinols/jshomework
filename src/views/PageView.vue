<template>
  <Header @loginStateChanged = "loginState =$event" @userLogedIn = "userData =$event"/>
  <Body :loggedIn = "loginState" :userData = "userData"/>
</template>

<script>
// @ is an alias to /src
import Header from '../components/Header.vue'
import Body from '../components/Body.vue'

export default {
  name: 'HomeView',
  data() {
    return{
      loginState: false,
      userData:{}
    }
  },
  components: {
    Header,
    Body
  }
}
</script>
