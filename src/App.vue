<template>
  <div class="container pt-5">
    <div class="row">
      <div class="col-2 left-nav-bar">
        <ul class="list-group">
          <li class="list-group-item p-0" aria-current="true" to="/">
            <router-link to="/">Задачи</router-link>
          </li>
          <li class="list-group-item p-0">
            <router-link to="/crm">CRM</router-link>
          </li>
        </ul>
      </div>
    </div>
  </div>
  <router-view/>
</template>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
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
