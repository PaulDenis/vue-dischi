<template>
    <div class="select">
        <select 
            name="seleziona_genere" 
            id="genere"
            v-model="selected"
            @change="$emit('SelectGenere', selected)"
        >
            <!-- <option 
                v-for="newgenere in generi"
                :key="newgenere"
                value="newgenere.genre">{{ newgenere.genre }}</option> -->
            <option value="">Nessun genere</option>
            <option value="Pop">Pop</option>
            <option value="Rock">Rock</option>
            <option value="Jazz">Jazz</option>  
            <option value="Metal">Metal</option>


        </select>
    </div>
</template>

<script>
export default {
    name: 'SelectGenere',
    props: [ 'generi' ],
    data: function() {
        return {
            selected: "",
            newGeneri: this.generi
        };
    },
    updated() {
        console.log(this.newGeneri);
    },
    methods: {

    }
    // computed: {
    //     newGeneri: () => {
    //     return this.generi.trim().toCapitalize()
    //     }
    // }
};
</script>

<style lang="scss" scoped>

    #genere {
        margin: 20px;
    }

</style>