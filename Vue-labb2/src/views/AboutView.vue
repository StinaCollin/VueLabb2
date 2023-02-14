<template>
  <div class="about">
    <h1>Dina sidor</h1>
    <div class="container text-center">
    <p>Logga in:</p>
    <div id="app">

            <div class="row align-items-start">
      <form @submit="onSubmit">
        <input v-model="userName">
        <input :disabled="userName.length === 0" type="submit" value="Logga in">
      </form>
      <p v-if="message !== null">{{ message }}</p>
    </div>
  </div>
</div>
  </div>
</template>
<script>

export default {
    data(){
      return {
        userName: '',
        message: null,
        error: 'Skriv in ditt namn',
      }
    },
    watch: {
       onEnter() {
        onSubmit()
      }
    },

    methods: {
      onSubmit(enter){
        enter.preventDefault();
        this.message  = `Välkommen ${this.userName}, du är nu inloggad!`
    },
  },
};


</script>
<style>

message{
    color:green;
}
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
