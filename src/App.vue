<template>
  <div id="app" class="container mt-5">
    <h1>My Shop</h1>
    <p class="animated fadeInRight">take a look at our</p>
    <font-awesome-icon icon="shopping-cart"></font-awesome-icon>
    
    <test :products="this.products" :maximum="this.maximum" ></test>
    <product-list :maximum="this.maximum" :products="this.products"></product-list>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import ProductList from "./components/ProductList.vue";


@Component({
  components: {
    FontAwesomeIcon,
    ProductList
  },
})
export default class App extends Vue {
  products: any;
  data() {
    return {
      maximum: 99,
      products: [
      {
        id: 1,
        name: "ice soap",
        descripiton: "this is soap",
        price: 22.45,
      },
      {
        id: 2,
        name: "colgate",
        descripiton: "this is for teath paste",
        price: 23.45,
      },
      {
        id: 3,
        name: "Oil",
        descripiton: "this is oil",
        price: 24.45,
      },
    ]
    };
  }
  mounted() {
    this.products = [
      {
        id: 1,
        name: "ice soap",
        descripiton: "this is soap",
        price: 22.45,
      },
      {
        id: 2,
        name: "colgate",
        descripiton: "this is for teath paste",
        price: 23.45,
      },
      {
        id: 3,
        name: "Oil",
        descripiton: "this is oil",
        price: 24.45,
      },
    ];
  }
}
</script>
