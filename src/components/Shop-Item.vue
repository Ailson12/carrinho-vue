<template>
    <div class="Item">

        <img :src="item.imageSrc" :alt="item.name" class="ItemImage">
        <div class="ItemDetails">
            <p><strong>{{item.name}}</strong></p>
            <p>Preço: <strong>R$ {{item.price}}</strong></p>
        </div>

        <!-- Button component -->
        <Shop-Button-Add
                @button-clicked="addToCart(item)"
                :item="item">
            <p>Adicionar ao carrinho</p>
        </Shop-Button-Add>

    </div>
</template>

<script>
import ShopButtonAdd from './Shop-Button-Add.vue'

    export default {
        name: 'Shop-Item',
        components: { ShopButtonAdd },
        props: ['item'],
        data() {
            return {}
        },

        methods: {
            addToCart(item) {
                this.$emit('update-cart', item)
            }
        }
    }
</script>

<style>

</style>
