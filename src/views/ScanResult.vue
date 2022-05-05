<template>
    <ion-page>
        <ion-content :fullscreen="true">

            <div class="main-container">

                <h2>Résultat</h2>
                <p></p>

                <div class="result-container">
                    <h3 class="product-title">Titre produit</h3>
                    <div class="allergenes-list">
                        <p>Allergene 1</p>
                        <p>Allergene 2</p>
                        <p>Allergene 3</p>
                    </div>
                    <p class="product-score ion-text-center">Nutri-score : D</p>
                </div>

            </div>

        </ion-content>
    </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonContent } from '@ionic/vue';


export default defineComponent({
    name: 'ScanResult',
    components: { IonContent, IonPage }
});
</script>

<style scoped>

ion-content {
    --background: #ebebeb;
}

.main-container h2 {
    font-family: peachy-keen-jf, sans-serif;
    text-align: center;
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
}

.allergenes-list {
    margin-top: 40px;
    margin-bottom: 40px;
}

</style>