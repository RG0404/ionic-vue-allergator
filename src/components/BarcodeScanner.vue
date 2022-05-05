<template>
  <div class="hello">
    <StreamBarcodeReader
      @decode="(a, b, c) => onDecode(a, b, c)"
      @loaded="() => onLoaded()"
    ></StreamBarcodeReader>
  </div>
</template>

<script>
import { StreamBarcodeReader } from "vue-barcode-reader";

export default {
  name: "HelloWorld",
  components: {
    StreamBarcodeReader,
  },
  data() {
    return {
      text: "",
      id: null,
    };
  },
  props: {
    msg: String,
  },
  methods: {
    onDecode(a, b, c) {
      console.log(a, b, c);
      this.text = a;
      if (this.text != ""){
        this.$router.push({path:'/scan-result/' + this.text});
      }
      if (this.id) clearTimeout(this.id);
      this.id = setTimeout(() => {
        if (this.text === a) {
          this.text = "";
        }
      }, 5000);
    },
    onLoaded() {
      console.log("load");
    },
  },
};
</script>
<style scoped>
.scanner-container {
    transform: rotateY(180deg);
}
</style>
