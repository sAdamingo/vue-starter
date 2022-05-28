<template>
  <div>
    <div v-if="isLogged">
       <login-form @login="logIn($event)"></login-form>
        </div>
    <div v-else>
        <h1>Witaj {{email}}</h1>
        <button class="logOut" @click="logIn()">Wyloguj!</button>
    </div>
  </div>
</template>

<script>
import 'milligram';
import LoginForm from "./LoginForm";
export default {
  data() {
    return {
      email:'',
      isLogged:true,
    }
  },
  methods: {
    alertMyEmail() {
      alert(this.email);
    },
    logIn(username) {
      this.email = username;
      this.isLogged = !this.isLogged;
    }
  },
  components: {LoginForm},
}
</script>

<style>
.warn {
  color:red;
  font-size: large;
}
.logOut {
  color: blue;
  text-underline-mode: true;
}
</style>
