<template>
  <div>
    <div v-if="isLogged">
        <h1>Twój e-mail to: {{email}}</h1>
      <h2>{{isLogged}}</h2>
        <div v-if="email.length < 10">Ale masz krótki adres!</div>

        <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
        <div class="warn" v-else>Twój adres e-mail jest stanowczo za długi.</div>
        <input type="email" v-model="email">
        <button @click="logIn()">Wyświetl mój e-mail w alercie</button>
        </div>
    <div v-else>
        <h1>Witaj {{email}}</h1>
        <a @click="logIn()">Wyloguj!</a>
    </div>
  </div>
</template>

<script>

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
    logIn() {
      this.isLogged = !this.isLogged;
    }
  }
}
</script>

<style>
.warn {
  color:red;
  font-size: large;
}
</style>
