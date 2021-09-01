<template>
  <div>
    <div class="row">
      <div class="image">
        <img
          v-if="formation.imgs"
          :src="require(`@/assets/${formation.imgs[0].Image}.jpg`)"
          class="card-img-top"
          alt="`${formation.image[0].image}`"
        />
      </div>

      <div class="nom">{{ formation.nom }}</div>
      <div class="desc">{{ formation.description }}</div>
      <div class="row">
        <div class="col-md-4" v-for="item in formation.videos" :key="item.id">
          <iframe width="250" height="250" :src="item.Video"> </iframe>
        </div>
      </div>
      <div class="pdf"></div>
    </div>
  </div>
</template>
<script>
export default {
    name: "showformation",
    data(){
        return {
            formation: {},
            id: this.$route.params.id,
        };
    },
    created() {
        this.axios.get("http://localhost:3000/formation/getById/" + this.id)
        .then((res) => {
            console.log(res);
            this.formation = res.data.formation;
        })
        .catch((err) => {
            alert(err);
        });
    },
};

</script>

<style>

</style>