<template>
    
    <div>

        <select @click="$emit('choiceMusic', typeOfMusic)" v-model="typeOfMusic" name="music" id="music">

            <option value="">All</option>

            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>

            <!-- <option v-for="(diskC, index) in diskAr" :key="index" :details="diskC" :value="diskC.genre">{{ diskC.genre }}</option> -->

        </select>

    </div>

</template>

<script>
import axios from 'axios';

export default {
    name: "TypeOfMusic",
    data: function(){

        return {

            typeOfMusic: [],

        };

    },
    created: function(){

    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
    .then((response) => {

      this.diskAr = response.data.response;
      console.log(this.diskAr);

    });

    }
};
</script>

<style scoped lang="scss">

</style>
