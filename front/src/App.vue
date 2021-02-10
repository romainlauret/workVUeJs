<template>
  <div id="app">
    <HeaderBar :loginInfos="login_infos"/>
    <router-view :username="login_infos.username" @userLogged="logUser"/>
  </div>
</template>

<script>
  import HeaderBar from './components/HeaderBar.vue';
  import Home from './views/Home.vue';
  import LoginPage from './views/LoginPage.vue';

  is_logged = false;
  username = "";
  export default {
    components: { HeaderBar, Home, LoginPage },
    data() {
          return {
            login_infos: {
              is_logged: false,
              username: '',
            }
          }
        },
        methods: {
          logUser(payload) {
            this.login_infos.is_logged = true;
            this.login_infos.username = payload.username;
          }
        },
  }
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
