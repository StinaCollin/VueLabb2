<script setup>
import ShopView from '../views/ShopView.vue'
</script>

<template>
    <div class="shop">
      <h1>Shop</h1>
      <div class="container text-center">
      <p>Logga in:</p>
      <div id="app">

              <div class="row align-items-start">
                <table>
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
            <td> {{product.price}}</td>
            <td><input @click="addToCart(index)" type="button" value="+"></td>
          </tr>

        </tbody>
      </table>
      <p>Totalsumma: {{total}}</p>

      </div>
    </div>
  </div>
    </div>
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
          'dd3ce0a3-1d30-4e3e-bcec-7095590019d9': {
            name: 'Jacket',
            price: 200,
            quantity: 0
          },
          'faf68d1f-8f3e-4668-891c-56118cc330f4': {
            name: 'Pants',
            price: 100,
            quantity: 0
          },
          'dd2bb41e-7f0a-4cb8-884b-588f9457dd54': {
            name: 'Shoes',
            price: 100,
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
