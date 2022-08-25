<template>
  <div class="app">
    <HeaderComponent />
    <div class="content">
      <NewProduct @add-product="addProduct" />
      <ProductItem />
    </div>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import ProductItem from './components/ProductItem.vue';
import HeaderComponent from './components/HeaderComponent.vue';
import NewProduct from './components/NewProduct.vue';

export default {
  name: 'App',
  components: {
    ProductItem,
    HeaderComponent,
    NewProduct
},
  data() {
    return {
      products: [
        {
          name: "Product 1",
          description: "Product 1 description"
        },
        {
          name: "Product 2",
          description: "Product 2 description"
        },
        {
          name: "Product 3",
          description: "Product 3 description"
        }
      ]
    }
  },
  methods: {
    addProduct(product) {
      // alert("Hello from App.vue: " + productName)
      console.log(product)
      this.products.push(product)
      console.log(this.products.length)
    }
  },
  //Using provide
  provide() {
    return {
      products: this.products,
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}
.content {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  margin: 3rem 1rem;
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}

</style>
