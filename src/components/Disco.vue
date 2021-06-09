<template>
    <div>
        <img :src="item.poster" alt="Copertina Disco">
        <p class="title">{{ item.title }}</p>
        <p class="author">{{ item.author }}</p>
        <p class="date">{{ item.year }}</p>
    </div>
</template>

<script>
export default {
    name: 'Disco',
    props:[ 'item' ]
}
</script>

<style lang="scss" scoped>

    div {
        height: 350px;
        width: 200px;
        margin: 20px ;
        text-align: center;
        font-weight: 700;
        font-size: 24px;
        img {
            height: 150px;
            margin: 25px
        };
        .title {
            padding: 0 20px;
            line-height: 24px;
            text-transform: uppercase;
            color: white;

        };
        .author, .date {
            margin: 0;
            font-size: 16px;
            color: #717571;
        }
        background-color: #2e3a46;
    }

    

</style>

