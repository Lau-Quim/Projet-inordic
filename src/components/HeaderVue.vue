<template>

    <header>

        <div class="logo">SH</div>

        <nav>
            <span v-for="i in menu">{{ i.name }}</span>
        </nav>

        <div class="login">Войти</div>
        <div class="basket">Корзина</div>

    </header>

</template>

<script>

    export default {
        name: "HeaderVue",
        data(){

            return {
                menu: [
                    {
                        name: 'Женщинам'
                    },
                    {
                        name: 'Мужчинам'
                    },
                    {
                        name: 'Детям'
                    },
                    {
                        name: 'Новинки'
                    },
                    {
                        name: 'О нас'
                    }
                ]
            };
        }
    }

</script>

<style scoped>

    header{
        display: flex;
        margin: 30px 30px 0;
        padding-bottom: 30px;
        align-items: center;
        border-bottom: 1px solid lightgrey;
    }

    .logo{
        padding: 10px;
        background-color: black;
        color: white;
        margin-right: 50px;
    }

    nav span:not(:last-child){
        margin-right: 30px;
    }

    .login{
        margin-left: auto;
        margin-right: 40px;
    }

</style>