<template>
    <div id="app">
        <HeaderVue></HeaderVue>
        <router-view/>
        <FooterVue></FooterVue>
    </div>
</template>

<script>

    import HeaderVue from './components/HeaderVue';
    import FooterVue from './components/FooterVue';

    export default {
        name: 'App',
        components: {HeaderVue, FooterVue}
    }

</script>

<style>

    @import url('https://fonts.googleapis.com/css?family=Roboto&display=swap');

    html{
        font-family: 'Roboto', sans-serif;
    }

    .uppercase{
        text-transform: uppercase;
    }

</style>
