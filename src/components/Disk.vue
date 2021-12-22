<template>

    <div class="diskCardContainer">

      <div class="diskImg">

        <img :src="details.poster" :alt="details.author">

      </div>

      <div class="diskInfo">

        <div class="title">

          {{ details.title }}

        </div>

        <div class="subtitle">

          <div class="author">

            {{ details.author }}

          </div>

          <div class="year">

            {{ details.year }}

          </div>

        </div>

      </div>

    </div>

</template>

<script>
export default {
  name: "Disk",
  props: {

    details: Object

  },
};
</script>

<style lang="scss" scoped>

  .diskCardContainer{

    background-color: #2e3a46;
    margin: 0 20px;
    width: calc( (100% / 5) - 40px );
    /* max-width: 165px; */
    /* min-width: 150px; */
    height: 300px;
    padding: 15px;
    padding-bottom: 35px;

    .diskImg{

      height: 150px;

      display: flex;
      justify-content: center;
      align-items: center;

      padding-bottom: 15px;


      img{

        height: 100%;

      }

    }

    .diskInfo{

      .title{

        color: white;
        text-transform: uppercase;
        font-weight: bold;
        text-align: center;
        font-size: 20px;
        margin-bottom: 15px;

      }

      .subtitle{

        color: gray;
        text-align: center;
        

        .author{

          font-size: 15px;

        }

        .year{

          font-size: 13px;

        }

      }

    }

  }

</style>