<script>
import axios from 'axios';

export default {
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
                url: 'http://localhost:4000/',
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
            <td><b>Produktnummer:</b> {{ productId }}</td>
        </tr>
    </table>
</template>

<style>
tr {
    text-align: center;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    margin: 10px 0;
    font-size: 16px;
}
</style>