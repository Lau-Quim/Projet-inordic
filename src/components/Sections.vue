<template>

    <div class="sections">

        <div class="item"
             v-for="(item, id) in items"
             :key="`item_${id}`">
            <div class="item_img"><img :src="item.PHOTO" alt=""/></div>
            <div class="item_name">{{ item.NAME }}</div>
            <div class="item_price">{{ item.PRICE }} {{ item.CURRENCY }}</div>
        </div>

    </div>

</template>

<script>

    export default {
        name: "Sections",
        data(){

            return {
                items: []
            };
        },
        mounted() {

            fetch(
                'http://192.168.64.2/api/goods.php',
                {
                    method: 'GET',
                    headers: {
                        'Accept': 'application/json',
                        'Content-Type': 'application/json'
                    },
                    mode: 'cors',
                }
            ).then(res => res.json()).then(res => {

                if(!!res && !res.err){

                    this.items = res.goods;

                    console.log(res);
                }
            });
        }
    }

</script>

<style scoped>

    .sections{
        display: flex;
        flex-wrap: wrap;
        flex-direction: row;
        width: 100%;
    }

    .sections > .item{
        width: 33%;
    }

    .sections > .item > .item_img{
        width: 95%;
        margin: 0 auto;
    }

    .sections > .item > .item_img > img{
        width: 100%;
        height: auto;
    }

    .sections > .item > .item_name{
        text-align: center;
        font-weight: bold;
        margin-top: 20px;
        font-size: .9rem;
    }

    .sections > .item > .item_price{
        text-align: center;
        font-size: .8rem;
        opacity: .8;
    }


</style>