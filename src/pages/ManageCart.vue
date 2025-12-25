<template>
    <div>
        <h2>ManageCart - Кошик</h2>
        <p v-if="cartItems?.length === 0">Cart is empty</p>
        <p v-if="cartItems?.length === 0">Кошик порожній</p>

        <ul class="cart__list" v-else>
            <li 
                class="item__cart"
                v-for="(item, index) in cartItems" :key="index"
                
            >
                <img 
                    :src="item.image" 
                    :alt="item.name" 
                    width="50"
                    class="cart__img _img"
                >
                <p>{{ item.name }} - {{ item.price }} грн</p>
            </li>
        </ul>

    </div>
</template>


<script>
    export default {
        name: "ManageCart",
        // data() {
        //     return ({
        //         cartItems: []
        //     })
        // },
        props: {
            cartItems: {
                type: Array,
                required: true
            }
        }
    }
</script>