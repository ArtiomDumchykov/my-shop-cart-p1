<template>
    <input type="number" v-on:input="handlerInitCounter">
    <p>message: {{message}}</p>


    <p>Count: {{count}}</p>
    <button v-on:click="increment">inc</button>
    <button v-on:click="decrement">dec</button>
    <button v-on:click="muvTen(10)">muv</button>
    <button v-on:click="increment2"  data-num="10">inc2</button>
</template>


<script>
    export default {
        name: "CounterPage",
        data() {
            return ({
                count: 0,
                message: ""
            })
        },
        methods: {
            increment() {
                // this.count = this.count + 1;
                this.count += 1;
            },
            decrement() {
                this.count -= 1;
            },
            muvTen(num) {
                this.count *= num;
            },
            increment2(event) {
                console.log(event)
                console.log(event.target)
                console.log(event.target.dataset)
                console.log(event.target.dataset.num)
                console.log(+event.target.dataset.num)
                console.log(Number(event.target.dataset.num))
                this.count += 1;
            },

            handlerInitCounter(event) {
                // this.count = event.target.value;
                this.count = +event.target.value;
                // this.count = Number(event.target.value);
                this.message = event.target.value
            }
        }
    }
</script>