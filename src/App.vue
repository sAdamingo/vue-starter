<template>
  <div>
    <div v-if="isLogged">
      <login-form @login="logIn($event)" button-label="Wejdź"></login-form>
      <login-form @login="logIn($event)" button-label="Wleć"></login-form>
      <login-form @login="logIn($event)" :button-label="Math.random() < 0.5 ? 'Etykieta A' : 'Etykieta B'"></login-form>        </div>
    <div v-else>
        <h1>Witaj {{email}}</h1>
      <meeting-page></meeting-page>
        <button class="logOut" @click="logIn()">Wyloguj!</button>
    </div>
  </div>
</template>

<script>
import 'milligram';
import LoginForm from "./LoginForm";
import MeetingPage from "@/MeetingPage";
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
  components: {MeetingPage, LoginForm},
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
