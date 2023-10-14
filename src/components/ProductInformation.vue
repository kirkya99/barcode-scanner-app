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
                url: 'https://backendappscanner.azurewebsites.net/',
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
            <td><b>Produktnummer:</b> {{ product }}</td>
        </tr>
    </table>
</template>