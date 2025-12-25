<template>
    <div>
        <hr>
        <ChildComponent v-on:message-sent="handler"/>
        <p>message: {{ message }}</p>
        <hr>
    </div>
</template>

<script>
import ChildComponent from './ChildComponent.vue';

    export default {
        name: "ParentComponent",
        components: {
            ChildComponent
        },
        data() {
            return ({
                message: ""
            })
        },
        methods: {
            handler(message) {
                this.message = message;
            }
        }
    }
</script>