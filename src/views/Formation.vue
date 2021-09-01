<template>
  <div>
      <myFormation :formations="formations"/>
  </div>
</template>

<script>
import myFormation from "../components/myformation"
export default {
    created () {
        this.axios.get("http://localhost:3000/formation/all")
        .then(res => {
            console.log(res.data);
            this.formations = res.data.formation
        })
        .catch(err => {
            alert(err);
        })
    },
    data () {
        return {
            formations: {}
        }
    },
        components: {
            myFormation
        },
}
</script>

<style>

</style>