<template>
<div v-if= "itemList.length > 0">
    <h3 class="text-center">Eklenen Ürünlerin Listesi</h3>
    <hr>
        <div class="row product-container">
            <app-items-added v-for= "product in itemList">
                <img class="card-img-top" :src="product.selectedImage" :alt="product.itemName">
                    <div class="card-body">
                        <h5 class="card-title">{{ product.itemName }}</h5>
                            <small><strong>Adet : </strong> {{ product.itemCount }}</small>
                            <br>
                            <small><strong>Fiyat : </strong> {{ product.itemPrice }}</small>
                            <br>
                            <small><strong>Tutar : </strong> {{ product.totalPrice }}</small>                   
                    </div>
            </app-items-added>
        </div>
</div>
</template>

<script>
import { eventBus } from "../main";
import itemsAdded from "./itemsAdded.vue";
export default {
    components : {
        appItemsAdded : itemsAdded,
    },
    data(){
        return {
            itemList: [],
        }
    },
    created(){
        eventBus.$on("itemAdded", (product) => {
            if(this.itemList.length < 10){
            this.itemList.push(product);
            eventBus.$emit("progressBarUpdated", this.itemList.length);
        } else{
            alert("Daha fazla ürün ekleyemezsiniz.")
        }
        }
        );
    }
}
</script>