<template>
    
    <div class="diskContainer">

        <Disk v-for="(diskC, index) in diskAr" :key="index" :details="diskC" />
        
    </div>

</template>

<script>
import axios from 'axios';
import Disk from "./Disk.vue";

export default {
  name: "DiskList",
  data: function(){

    return {

      diskAr: [],

    };

  },
  components: {
    Disk,
  },
  created: function(){

    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((response) => {

      this.diskAr = response.data.response;

    });

  }
};
</script>

<style lang="scss" scoped>

    .diskContainer{

        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        width: 70%;
        height: 100%;
        margin: auto;

    }

</style>