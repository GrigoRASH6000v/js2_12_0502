<template>
    <div>
        <header>
            <div class="logo">E-shop</div>
            <div class="cart">
                <search />
                <button class="btn-cart" type="button" @click="showCart = !showCart">Корзина</button>
                <cart v-show="showCart" ref="cartReference" />
            </div>
        </header>
        <main>
            <catalog ref="catalogReference" />
        </main>
    </div>
</template>

<script>
import catalog from '../components/catalog.vue'
import cart from '../components/cart.vue'
import search from '../components/search.vue'

export default {
    data() {
        return {
            showCart: false,
            // API: 'https://raw.githubusercontent.com/aleksey-lee/js2_12_0502/master/students/aleksey-lee/project/webpack/src/server/db'
        }
    },
    components: {
        catalog,
        cart,
        search
    },
    methods: {
        getData(url) {
            return fetch(url).then(d => d.json())
        }
    }
}
</script>

<style>

</style>