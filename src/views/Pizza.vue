<template>
<div>
   <center>
      <h1 id="title">{{pizzas[id].name}}</h1>
   </center>

   <router-link to="/menu">
      <button class="back-button button">Back</button>
   </router-link>

   <section class="about-box">
      <div class="box">
         <img id="product-pic" :src="'/images/pizzas/' + pizzas[id].img" />
      </div>

      <div></div>

      <div class="box word-box">
         <br>
         <h3>${{sizes[selected].price}}</h3>
         <br>

         <p>{{pizzas[id].description}}</p>

         <br>

         Size:
         <select v-model="selected">
            <option v-for="size in sizes" :key="size.id" v-bind:value="size.id">
               {{ size.size }}
            </option>
         </select>

         <br><br><br>

         <center>
            <button class=" order-button button">Add to Order</button>
         </center>

      </div>
   </section>
</div>
</template>

<script>
export default {
   name: 'Pizza',
   data() {
      return {
         id: this.$route.params.id,
         selected: 2,
      }
   },
   computed: {
      pizzas() {
         return this.$root.$data.pizzas;
      },
      sizes() {
         return this.$root.$data.sizes;
      }
   },
}
</script>
