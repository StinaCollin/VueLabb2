<template>
  <div class="about">
    <h1>Dina sidor</h1> <div> <img src="../assets/img/love-plant1.png" alt="heart" width="170">
    <div class="container text-center">
        <div>
    <p>Logga in:</p>
    <div id="app">
        <!-- Form input -->
        <div class="row align-items-start">
      <form @submit="onSubmit">
        <input v-model="userName">
        <!-- Disabled button -->
        <input :disabled="userName.length === 0" type="submit" value="Logga in">
      </form>
      <!-- Text interpolation -->
      <p id="welcome" v-if="message !== null">{{ message }}</p>
    </div></div>
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


p {
    font-weight: bold;
    margin-top: 2rem;
}

 #welcome {
    font-weight: bold;
    font-style: italic;
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
