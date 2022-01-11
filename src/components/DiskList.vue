<template>
    
  <div class="containerTotal">

    <div class="choiceM">

      <TypeOfMusic @choiceMusic="choiceTypeOfMusic" />

    </div>

    <div class="diskContainer">

      <Disk v-for="(diskC, index) in filterMusic" :key="index" :details="diskC" />
        
    </div>

  </div>

</template>

<script>
import axios from 'axios';
import Disk from "./Disk.vue";
import TypeOfMusic from "./TypeOfMusic.vue";

export default {
  name: "DiskList",
  data: function(){

    return {

      diskAr: [],
      choiseMusicType: ""

    };

  },
  components: {
    Disk,
    TypeOfMusic,
  },
  methods: {

    choiceTypeOfMusic: function(tOM){

      this.choiseMusicType = tOM;

    },

  },
  computed: {

    filterMusic: function(){

      if(this.choiseMusicType.length === 0){

        return this.diskAr;

      }
      else{

        const filteredArray = this.diskAr.filter((element) => {

          return element.genre.toLowerCase().includes(this.choiseMusicType.toLowerCase());

        });

        return filteredArray;

      }
      
    }

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

    .containerTotal{

      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100%;
      margin: auto;

      .choiceM{

        margin-top: 20px;

      }

      .diskContainer{

        display: flex;
        justify-content: center;
        align-items: center;
        flex-wrap: wrap;
        width: 70%;
        height: 100%;
        margin: auto;

      }

    }

</style>