<!-- Hann tyvärr inte göra klart denna shop -->

<script setup>
import ShopView from '../views/ShopView.vue'
</script>

<template>
    <div class="shop">
        <h1>Shoppa loss här :)</h1>
      <div>
      <p>Våra produkter:</p>
        <!-- Shop cards -->
        <div class="card" style="width: 18rem">
            <img
                src="../assets/img/love-plant.png"
                width="28"
                class="card-img-top"
                alt="contact"
            />
            <div class="card-body">
                <!-- Text interpolation -->
                <h5 class="card-title">Namn: {{ list.name }}</h5>
                <p class="card-text"> Telefon: {{ list.phone }}
                </p>
                <a href="#" class="btn btn-primary">Kontakta mig här</a>
            </div>
        </div>
    </div>
        </div>


    <!-- <div class="shop">
      <h1>Shoppa loss här :)</h1>
      <div class="container text-center">
      <p>Våra produkter:</p>
      <div id="app">

              <div class="row align-items-start"> -->
                <!-- <table>
        <thead>
          <tr>
            <th>Produkt </th>
            <th>Antal </th>
            <th>Pris </th>
          </tr>
        </thead>
        <tbody>
          <tr :key="(product, index) in products">
            <td>{{product.name}}</td>
            <td>{{products.quantity}}</td>
            <td> {{products.price}}</td>
            <td><input @click="addToCart(index)" type="button" value="+"></td>
          </tr>

        </tbody>
      </table> -->
      <!-- <p>Totalsumma: {{total}}</p>

      </div>
    </div>
  </div>
    </div> -->
  </template>


  <script>
  export default {
    computed: {
      total() {
        return Object.values(this.products).reduce(
          (accumulator, value) => accumulator + value.price * value.quantity,
          0
        )
      }
    },
    data() {
      return {
        products: {
          '1': {
            name: 'Blomsterbukett Small',
            price: 100,
            quantity: 0
          },
          '2': {
            name: 'Krukväxt Medium',
            price: 100,
            quantity: 0
          },
          '3': {
            name: 'Blomsterbukett Lyx',
            price: 300,
            quantity: 0
          }
        }
      }
    },
    methods: {
      addToCart(productId) {
        this.products[productId].quantity++
      }
    },
  };

  </script>


  <style>

  @media (min-width: 1024px) {
    .shop {
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
  }
  </style>
