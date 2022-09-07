<template>
  <div class="login-from" v-bind:class="loginFormVisible">
    <div class="container h-100">
      <div class="row h-100 justify-content-center align-items-center">
        <div class="col-lg-3 col-md-6 col-sm-12">
          <div class="card p-2">
            <div class="p-2">
              <input type="text" class="form-control" placeholder="login" v-model="email">
            </div>
            <div class="p-2">
              <button class="btn btn-outline-info w-100" v-on:click="userLogin">
                <i class="fa fa-sign-in" aria-hidden="true"></i>
              </button>
            </div>
            <div class="container preloader">
              <div class="row justify-content-center">
                <div class="col" v-bind:class="preloaderVisible">
                  <div class="spinner-border text-info" role="status"></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        email: '',
        preloaderVisible: 'unvisible',
        loginFormVisible: 'visible',
      };
    },
    methods: {
      userLogin: async function () {
        if (!this.email) {
          alert('Укажите email!');
        } else {
          this.preloaderVisible = 'visible';
          var user = await $.get(this.$store.state.apiUrl+'user.get.json?EMAIL='+this.email);
          this.preloaderVisible = 'unvisible';
          if (!user.result[0]) {
            alert('Пользователь с таким email отсутствует в базе!');
          } else {
            this.$store.state.user = user.result[0];
            this.loginFormVisible = 'unvisible';
          }
        }
      }
    },
    mounted: function () { // УДАЛИТЬ
      this.email = 'ra@ck.by';
      this.userLogin();
    }
  };
</script>

<style scoped>
  .login-from {
    position: fixed;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
    background: CadetBlue;
  }
  .unvisible {
    display: none;
  }
  .visible {
    display: block;
  }
  .preloader {
    height: 50px;
  }
</style>