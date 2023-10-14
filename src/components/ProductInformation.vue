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
                url: 'https://backendscannerapp.azurewebsites.net/',
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
    <table>
        <tr v-for="product in productArray">
            <p><b>Produktnummer:</b> {{ productId }}</p>
            <p><b>Produktname:</b> {{ productName }}</p>
            <img :src="productImage" alt="Kein Bild des Produkts verfügbar"/>
        </tr>
    </table>
</template>