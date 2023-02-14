<script setup>
import WelcomeItem from './WelcomeItem.vue'
import DocumentationIcon from './icons/IconDocumentation.vue'
import ToolingIcon from './icons/IconTooling.vue'
import EcosystemIcon from './icons/IconEcosystem.vue'
import CommunityIcon from './icons/IconCommunity.vue'
import SupportIcon from './icons/IconSupport.vue'
import ContactUsVue from './ContactUs.vue'

import http from 'node:http';
import https from 'node:https';
import ShopView from '../views/ShopView.vue'
import ShopHere from '../components/ShopHere.vue'
import ContactUs from '../components/ContactUs.vue'
</script>

<template>

    <img src="../assets/img/bouquet_hero.jpg" alt="Hero" width="500">

        <!-- Textinterpolering -->
         <h2 class="title">{{ message }}</h2>
         <!-- Fetch -->
    <div id="contact">
        <div class="container text-center">
            <div class="row align-items-start">

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
        /* mounted () : it will executed before creating the component. created () : it will executed after creating the component for render. */
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
    }
    .title,
    h2 {

        justify-content: center;
        margin-top: 3vh;
    }
</style>
