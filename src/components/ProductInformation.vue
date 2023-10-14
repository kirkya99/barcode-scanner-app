<script>
import axios from 'axios';

    export default{
        // props: ['idNumber'],
        created() {
            this.fetchList()
        },
        data() {
            return {
                productArray: []
            }
        },
        methods: {
            fetchList() {
            const options = {
                method: 'GET',
                //url: ,
                //headers: {
                //}
            }

            axios.request(options)
                .then(response => {
                    this.productArray = response.data
                })
                .catch(console.error);
        },
        }
    }
</script>

<template>
    <p><b>Produktnummer:</b> {{ productId }}</p>
    <p><b>Produktname:</b> {{ productName }}</p>
    <img :src="productImage" alt="Kein Bild des Produkts verfügbar"/>
</template>