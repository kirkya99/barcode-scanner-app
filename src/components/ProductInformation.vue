<script>
    export default{
        // props: ['idNumber'],
        data() {
            return {
                productId: 1,
                productName: "Product",
                productImage: "Product.png"
            }
        }
    }
</script>

<template>
    <p><b>Produktnummer:</b> {{ productId }}</p>
    <p><b>Produktname:</b> {{ productName }}</p>
    <img :src="productImage" alt="Kein Bild des Produkts verfügbar"/>
</template>