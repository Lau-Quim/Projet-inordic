<template>

    <div class="banner">

        <div class="main_title uppercase">{{ title }}</div>
        <div class="sub_title">{{ subtitle }}</div>
        <div class="button uppercase">{{ button }}</div>

    </div>

</template>

<script>

    export default {
        name: "Banner",
        data() {

            return {
                title: 'Новые поступления весны',
                subtitle: 'Мы подготовили для Вас лучшие новинки сезона',
                button: 'Посмотреть новинки'
            };
        }
    }

</script>

<style scoped>

    .banner {
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 7rem;
    }

    .main_title {
        font-size: 3rem;
        font-weight: bold;
        text-align: center;
    }

    .sub_title {
        margin-top: 1rem;
        font-size: 1.5rem;
        font-style: italic;
        color: grey;
    }

    .button {
        margin-top: 3rem;
        border: 1px solid lightgrey;
        padding: 20px;
        font-size: 0.8rem;
        transition: 1s;
        color: lightgrey;
    }

    .button:hover{
        cursor: pointer;
        background-color: lightgrey;
        color: white;
        border: 1px solid white;
        transition: 1s;
    }

</style>