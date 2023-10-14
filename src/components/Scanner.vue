<script>
import { StreamBarcodeReader } from "vue-barcode-reader";
import axios from 'axios'

export default {
  // TODO: Add Emits
  emits: ['addToList'],
  components: {
    StreamBarcodeReader,
  },
  data() {
    return {
      decodedText: ""
    };
  },
  methods: {
    onDecode(result) {
      this.decodedText = result;
      // sendId()
    },
    onLoaded() {
      console.log("Scanner loaded and ready!");
    },
    // onError(error) {
    //   console.error("Error while scanning:", error);
    // },
    sendId() {
      axios.post('http://localhost:4000/setProducts', this.decodedText)
    }
  }
};
</script>

<template>
  <div id="app">
    <div id="pic">
      <!-- <h1>Barcode & QR Code Scanner</h1> -->


      <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
    </div>
  </div>
  <div v-if="decodedText">
    <h2>Decoded Text:</h2>
    <p>{{ decodedText }}</p>
    <button @click="sendId">Save Barcode</button>
  </div>
</template>

<style>
body {
  background-color: rgb(176, 253, 167);
}

div {
  text-align: center;
}

#pic {
  border: 2.5px solid black;
  padding: 5px;
  text-align: center;
}

button {
  background-color: #019626;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #9dff00;
}
</style>