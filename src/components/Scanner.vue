<script>
import { StreamBarcodeReader } from "vue-barcode-reader";

export default {
  name: "App",
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
    },
    onLoaded() {
      console.log("Scanner loaded and ready!");
    },
    onError(error) {
      console.error("Error while scanning:", error);
    }
  }
};
</script>


<template>
    <div id="app">
      <h1>Barcode & QR Code Scanner</h1>
  
      
      <StreamBarcodeReader @decode="onDecode" @loaded="onLoaded"></StreamBarcodeReader>
  
      <div v-if="decodedText">
        <h2>Decoded Text:</h2>
        <p>{{ decodedText }}</p>
      </div>
    </div>
  </template>