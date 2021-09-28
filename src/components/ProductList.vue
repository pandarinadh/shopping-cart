<template>
  
 <div>
  <transition-group
    name="fade"
    tag="div"
    @beforeEnter="beforeEnter"
    @enter="enter"
    @leave="leave"
  >

   here in product list
     <div  class="row mb-3 align-items-center"  v-for="(item, index) in this.products"   :key="index"  :data-index="index" >
          <div class="col-1 m-auto"></div>
          <button class="btn btn-info">+</button>
         
          <div class="col">
            <h3 class="text-info">{{ item.name }}</h3>
            <p class="mb-0">{{ item.description }}</p>
            <div class="h5 float-right">
              <Price :value="Number(item.price)"></Price>
            </div>
          </div>
      </div>
   
  </transition-group>
  </div>
</template>

<script>

import Price from "./price.vue";

export default ({
    name:"product-list",
  components: { Price },
  
  props: ["products", "maximum"],

  data() {
    return{
    //  products:null
    }
  },
  methods: {
    beforeEnter: function (el) {
      el.className = "d-none";
    },
    enter: function (el) {
      var delay = el.dataset.index * 100;
      setTimeout(() => {
        el.className = "row d-flex mb-3 align-tems-center animated fadeIn";
      }, delay);
    },
    leave: function (el) {
      var delay = el.dataset.index * 100;
      setTimeout(() => {
        el.className = "row d-flex mb-3 align-tems-center animated fadeOut";
      }, delay);
    },
  },

  
});
</script>
