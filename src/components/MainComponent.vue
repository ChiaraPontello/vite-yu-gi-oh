<template>
    <section class="m-10">
    <div class="text-center bg-card container">
        <div>
            <img :src="image" :alt="name" class="card" >
        </div>
        <h3>{{ name }}</h3>
        <h4>{{ archetype }}</h4>
    </div>
</section>
</template>

<script>
export default {
    name: "MainComponent",
    data() {
        return {}
    },
    props: {
        image: String,
        name: String,
        archetype: String
    }
}
</script>

<style lang="scss" scoped>


.card{
    width: 100%;
    display: block;
    margin-bottom: 20px;
}
.bg-card{
    background-color: rgb(212, 143, 56);
}
h3{
    font-size: 1.2rem;
    color: white;
    margin-bottom: 20px;
}
h4{
    font-size: 1rem;
    margin-bottom: 30px;
}

</style>