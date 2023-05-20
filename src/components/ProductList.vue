<template>
 <div class="mt-16 max-width mx-auto">
    <ProductCard :datas="pData"/>
 </div>
</template>

<script>
import ProductCard from './ProductCard.vue';
import productData from '../assets/stays.json'

    export default {
    components: { ProductCard },
    data() {
        return {
            pData: productData
        }
    }
    
}
</script>

<style scoped>
.max-width {
    max-width: 90%;
}
</style>