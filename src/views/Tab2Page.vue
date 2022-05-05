<template>
  <ion-page>
    <ion-content :fullscreen="true">
      
    <StreamBarcodeReader
      @decode="(a:any, b:any, c:any) => onDecode(a, b, c)"
      @loaded="() => onLoaded()"
    ></StreamBarcodeReader>
    Input Value: {{ text || "Nothing" }}
      
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonContent } from '@ionic/vue';
import { StreamBarcodeReader } from 'vue-barcode-reader';

export default defineComponent({
  name: 'Tab2Page',
  components: { 
    IonContent, IonPage,StreamBarcodeReader 
  },
  data() {
    return {
      text: "",
      id: -1,
    };
  },
  props: {
    msg: String,
  },
  methods: {
    onDecode(a:any, b:any, c:any) {
      console.log(a, b, c);
      this.text = a;
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
});
</script>
