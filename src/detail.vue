<template>

    <div class="detail">
        <div class="detail_img">
            <img :src="item['Photo'][0]"/>
        </div>

        <div class="detail_name"> {{item['Name']}} </div>

        <div class="detail_vendor-code"> {{item['Id']}} </div>

        <div class="detail_price"> {{item['Price']}} </div>

        <div class="detail_description"> {{item['Description']}} </div>
        <div class="detail_size">
            <span>Size</span>
            <div v-for="(size, id) in item['Size']" :key="`size_${id}`">
                {{size}}
            </div>
        </div>
    <div class="detail_button">Insert into box</div>
    </div>
</template>

<script>
    export default{
        name: "detail",
        props: {
            id: String
        },
        data(){
            return{
                item: {}
            };
        },
        mounted(){
            fetch( 
                'http://localhost/Nordic%20Aulas/ProjLast/index.php',
                {
                    method: 'POST',
                    headers: {
                        'Accept': 'application/json',
                        'Content-Type': 'application/json'
                    },
                    mode: 'cors',
                    body: JSON.stringify({id: this.id})
                    }
                ).then(res => res.json()).then(res => {
                console.log(res);
                this.item = res;
            });
        }
    }
</script>

<style scoped>
    .detail{
        display: flex;
        flex-direction: column;
        align-items: center;
        margin-top: 1rem;

    }
    .detail .detail_name{

    }
    .detail .detail_vendor-code{
        
    }
    .detail .name{
        
    }
</style>