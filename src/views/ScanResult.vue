<template>
    <ion-page>
        <ion-content :fullscreen="true">

            <div class="main-container">

                <h2>Résultat</h2>
                <p></p>

                <div class="result-container">
                    <h3 class="product-title">{{product.product_name}}</h3>
                    <div class="allergenes-list">
                        <p class="list-title">Allergènes présents dans le produit :</p>
                        <p>{{ product.allergens }}</p>
                    </div>
                    <p class="product-score ion-text-center">Nutri-score : {{product.nutriscore_grade}}</p>
                </div>

                <ion-buttons>
                    <ion-back-button>Retour</ion-back-button>
                </ion-buttons>

            </div>

        </ion-content>
    </ion-page>
</template>

<script lang="ts">
/*ts-ignore*/
import { defineComponent } from 'vue';
import { IonPage, IonContent, IonButtons } from '@ionic/vue';
import { useRoute } from 'vue-router';


export default defineComponent({
    name: 'ScanResult',
    components: { IonContent, IonPage, IonButtons },
    data(){
        return {
            loading: false,
            error: null,
            product: "",
        }
    },
    created() {
        this.$watch(
            () => this.$route.params,
            () => {
                this.fetchData()
            },
            {immediate: true}
        )
    },
    methods: {
        fetchData() {
            this.loading = true
            fetch('https://world.openfoodfacts.org/api/v0/product/' + this.$route.params.productId + '.json').then((res)=> res.json()).then((res:any)=>{
                this.loading = false
                this.product=res.product
                console.log(res)
            }).catch((err)=>{
                if (err) {
                    this.error = err.toString()
                }
            })
        }
    },
    // async created() {
    //     const response = await fetch(
            
    //     )
    // },
    // setup() {
    //     const route = useRoute();
    //     this.url = https://world.openfoodfacts.org/api/v0/product/ + productId + .json
    //     console.log(route.params.productId);
    // }
});
</script>

<style scoped>

ion-content {
    --background: #48BF53;
}

.main-container h2 {
    font-family: peachy-keen-jf, sans-serif;
    text-align: center;
    color: #fff;
}

.main-container {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.result-container {
    width: 90%;
    border-radius: 24px;
    background-color: #fff;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    padding: 20px 30px;
    font-family: poppins, sans-serif;
}

.product-title {
    font-family: poppins, sans-serif;
    font-size: 28px;
    color: #11823B;
    font-weight: bold;
}

.allergenes-list {
    margin-top: 30px;
    margin-bottom: 40px;
}

.list-title {
    font-size: 18px;
}

.product-score {
    font-size: 22px;
}

ion-buttons {
    position: absolute;
    bottom: 50px;
    left: 50%;
    transform: translateX(-50%);
    color: #fff;
    font-family: poppins, sans-serif;
    font-size: 36px;
    background-color: #11823B;
    border-radius: 20px;
    padding: 8px 40px;
    box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;   
}

</style>