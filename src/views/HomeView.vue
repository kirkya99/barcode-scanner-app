<script>
import Scanner from '../components/Scanner.vue'
import ProductInformation from '../components/ProductInformation.vue';

export default {
  components: {
    Scanner, ProductInformation
  },
  data() {
    return {
      id: ""
    }
  }
}
</script>

<template>
  <main>
    <Scanner />
    <ProductInformation />
  </main>
</template>
