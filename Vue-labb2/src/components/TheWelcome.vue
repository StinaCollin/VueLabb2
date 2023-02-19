<script setup>
import ShopView from '../views/ShopView.vue'
import ShopHere from '../components/ShopHere.vue'
import ContactUs from '../components/ContactUs.vue'
</script>

<template>

    <img src="../assets/img/bouquet_hero.jpg" alt="Hero" width="500">

        <!-- Textinterpolation -->
         <h2 class="title">{{ message }}</h2>

    <div id="contact">
        <!-- Bootstrap cards -->
        <div class="container text-center">
            <div class="row align-items-start">
                <!-- Fetch API for each item in API list -->
               <contact-us v-for="user in list"  :key="user.name" :list="user"/>

            </div>
        </div>
    </div>


</template>
<script>
    export default {
        data() {
            return {
                message: 'Du är alltid välkommen att kontakta någon av oss som jobbar här:',
                list: [],

            }
        },
        components: { 'contact-us': ContactUs },
         mounted() {
            this.fetchData()
        },
        methods: {
            async fetchData() {
                const res = await fetch('https://jsonplaceholder.typicode.com/users/')
                const result = await res.json()
               this.list = result
            }
        }
    }
</script>
<style>
    #contact {
        justify-content: center;
        margin-top: 5vh;
        margin-bottom: 5vh;
        border: 1;
    }
    .title,
    h2 {

        justify-content: center;
        margin-top: 3vh;
        margin-bottom: 3vh;
    }
</style>
