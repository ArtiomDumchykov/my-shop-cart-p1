<template>
   <input type="text" v-on:input="handlerMessage">
   <input type="text" v-model="text" v-on:input="handlerMessage2">
</template>

<script>
    export default {
        data() {
            return ({
                text: ""
            })
        },
        methods: {
            handlerMessage(event) {
                const msg = event.target.value;
                this.$emit("message-sent", msg)
            },
            handlerMessage2() {
                const msg = this.text;
                this.$emit("message-sent", msg);
            },
        },
        emits: ['message-sent'], // ✅ ОБОВʼЯЗКОВО
    }
</script>