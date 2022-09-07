<template>
  <div class="container">
    <div class="row justify-content-end">
      <div class="col-lg-2 col-md-4 col-sm-6 text-right">
        <i class="fa fa-user-o" aria-hidden="true"></i>
        {{$store.state.user.EMAIL}}
      </div>
    </div>
  </div>
  <div class="container pt-5">
    <div class="row">
      <div class="col-lg-2 col-md-4 col-sm-12 left-nav-bar">
        <ul class="list-group">
          <li class="list-group-item p-0" aria-current="true" to="/">
            <router-link to="/">Задачи</router-link>
          </li>
          <li class="list-group-item p-0">
            <router-link to="/crm">CRM</router-link>
          </li>
        </ul>
      </div>
      <div class="col-lg-10 col-md-8 col-sm-12">
        <router-view/>
      </div>
    </div>
  </div>  
  <LoginFrom/>
</template>

<script>
  import LoginFrom from './components/LoginForm.vue';
  export default {
    components: {
      LoginFrom,
    }
  };
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
  }
  .left-nav-bar a {
    color: grey;
    text-decoration: none;
    display: block;
    height: 100%;
    font-weight: 100%;
    outline: none;
    padding: 5px;
  }

  li a.router-link-exact-active {
    color: red;
  }

</style>
