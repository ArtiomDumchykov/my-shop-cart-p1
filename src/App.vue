<template>
    <div id="app">

        <CounterPage />
        <ParentComponent />


        <router-view></router-view>
        <FooterComponent />
    </div>
</template>

<script>
import FooterComponent from './components/FooterComponent.vue';
import ParentComponent from './components/ParentComponent.vue';
import CounterPage from './pages/CounterPage.vue';


export default {
    components: {
        FooterComponent,
        CounterPage,
        ParentComponent
    },
};
</script>
