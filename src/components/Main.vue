<template>

    <div>

        <Banner></Banner>
        <ListTile></ListTile>
        <Subscribe></Subscribe>

    </div>

</template>

<script>

    import Banner from './Banner';
    import ListTile from './ListTile';
    import Subscribe from './Subscribe';

    export default {
        name: 'Main',
        components: {Banner, ListTile, Subscribe}
    };

</script>

<style scoped>

</style>