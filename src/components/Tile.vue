<template>

    <div class="tile" :class="{'tail': isTail}">

        <img v-if="!!img" :src="img"/>

        <div class="tile_body">
            <div class="title" v-if="!!title">{{ title }}</div>
            <div class="sub_title" v-if="!!subtitle">{{ subtitle }}</div>
        </div>
    </div>

</template>

<script>
    export default {
        name: "Tile",
        props: {
            isTail: {
                type: Boolean,
                default: false
            },
            title: {
                type: String,
                required: false
            },
            subtitle: {
                type: String,
                required: false
            },
            img: {
                type: String,
                required: false
            }
        }
    }
</script>

<style scoped>

    .tile {
        /*width: 25%;*/
        box-sizing: border-box;
        position: relative;
        display: flex;
        flex-direction: column;

        background-color: lightgrey;
        border: 1px solid black;
    }

    .tail{
        grid-row: span 2;
    }

    .tile_body{
        margin: auto 0;
        text-align: center;
    }

    img {
        position: absolute;
        width: 100%;
        height: 100%;
    }

</style>