<template>
    <section class="dischi">
        <div v-if="dischi.length > 0" class="container">
            <Disco
            v-for="disco in dischi"
            :key="disco.title"
            :item="disco"
            />
        </div>
        <Loader v-else />
    </section>
</template>

<script>
import axios from 'axios';
import Disco from './Disco'
import Loader from './Loader.vue'

export default {
    name: 'ContenitoreDischi',
    components: {
        Disco,
        Loader
    },
    data: function() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            dischi: []
        };
    },
    created: function() {
        axios
            .get(this.apiUrl)
            .then(
                (response) => {
                    console.log(response)
                    this.dischi = response.data.response;
                    console.log(this.dischi);

                }
            )
            .catch();
    },
    mounted: function () {


    }
    
}
</script>

<style lang="scss" scoped>

    .dischi {
        
        height: calc(100vh - 75px);
        margin-top: 75px;
        overflow-y: auto;
        background-color: #1e2d3b;
    }
    .container {
        display: flex;
        justify-content: space-around;
        flex-wrap: wrap;
    }

</style>