<template>
    <section class="dischi">
        <SelectGenere
        @SelectGenere="selezioneGenere"
        :generi="dischi"
        />
        <div
        v-if="dischi.length > 0"
        class="container">
            <Disco
            v-for="disco in generiFiltrati"
            :key="disco.title"
            :item="disco"
            />
        </div>
        <Loader v-else />
    </section>
</template>

<script>
import axios from 'axios';
import Disco from './Disco';
import Loader from './Loader.vue';
import SelectGenere from './SelectGenere.vue';


export default {
    name: 'ContenitoreDischi',
    components: {
        Disco,
        Loader,
        SelectGenere
    },
    data: function() {
        return {
            apiUrl: 'https://flynn.boolean.careers/exercises/api/array/music',
            dischi: [],
            newGenere: ""
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
    computed: {
        generiFiltrati: function() {
            const newArray = this.dischi.filter(
                (element) => {
                    return element.genre.includes(this.newGenere);
                }
            );
            // console.log(newArray);
            return newArray;
        }
    },
    methods: {
        selezioneGenere(genere) {
            this.newGenere = genere;
            console.log(this.newGenere);
        }
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
    .select {
        position: absolute;
        top: 0;
        right: 20px;
    }

</style>