<template>
    <div>
        <h2>ManageCart - Кошик</h2>
        <p v-if="cartItems?.length === 0">Cart is empty</p>
        <p v-if="cartItems?.length === 0">Кошик порожній</p>
        
        <p v-if="cartItems?.length !== 0">totalPrice: {{ totalPrice }}</p>
        
        <ul 
            v-if="cartItems?.length !== 0"
            class="cart__list"
        >
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

                <button 
                    class="buy-button"
                    v-on:click="onRemoveToCart(index)"
                >
                    Видалити
                </button>
                    
                
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
            },
            totalPrice: {
                type: Number
            }
        },
        methods: {
            onRemoveToCart(index) {
                console.log(index)
                this.$emit("message-remove-to-cart", index)
            }
        }
    }
</script>


<!-- Приклад домашнього завдання -->

<style scoped>
div {
    background-color: white;
    width: 90%;
    margin: 30px auto;
    text-align: center;
    border-radius: 10px;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin: 10px;
}

button {
    background: red;
    color: white;
    border: none;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background: darkred;
}
</style>