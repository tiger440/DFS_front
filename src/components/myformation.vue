<template>
    <div class="row">
        <div class="card" style="width: 18rem;" v-for="formation in formations" :key="formation.id">
            <img v-if="formation.imgs" :src="require(`@/assets/${formation.imgs[0].Image}.jpg`)" class="card-img-top" alt="...">
            <div class="card-body">
                <h5 class="card-title">{{ formation.nom }}</h5>
                <p class="card-text">{{ formation.description }}</p>
                <router-link :to="`/showformation/${formation.id}`">
                    <a href="#" class="btn btn-primary"></a>
                </router-link>
                
            </div>
        </div>
    </div>
</template>

<script>
export default {
        name: "myformation",
        props: ["formations"],
        data () {
        return {
        }
    },
    created () {
    },
    
    methods: {

    },
    
}
</script>

<style>

</style>