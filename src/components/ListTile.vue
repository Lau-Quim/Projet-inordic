<template>

    <div class="list">

        <Tile v-for="(i, id) in tiles"
              :key="`tile_${id}`"
              :is-tail="i.isTail"
              :title="i.title"
              :subtitle="i.subtitle"
              :img="i.img">
        </Tile>

    </div>

</template>

<script>

    import Tile from './Tile';

    export default {
        name: "ListTile",
        components: {Tile},
        data(){

            return {
                tiles: [
                    {
                        title: 'Джинсовые куртки',
                        subtitle: 'от 3200руб',
                        isTail: true
                    },
                    {
                        title: 'Элегантная обувь',
                        subtitle: 'ботинки, кроссовки',
                        isTail: false
                    },
                    {
                        title: 'Спортивная одежда',
                        subtitle: 'от 590руб',
                        isTail: false
                    },
                    {
                        title: 'Детская одежда',
                        isTail: false
                    },
                    {
                        subtitle: 'аксессуары',
                        isTail: false
                    },
                    {
                        title: 'Джинсы',
                        isTail: false
                    },
                ]
            };
        }
    }

</script>

<style scoped>

    .list{
        margin-top: 2rem;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr;
        grid-auto-flow: dense;
        grid-auto-rows: 356px;
    }

</style>