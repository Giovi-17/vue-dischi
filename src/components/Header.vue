<template>
    <header>

        <div class="logo">

            <img src="https://storage.googleapis.com/pr-newsroom-wp/1/2018/11/Spotify_Logo_RGB_Green.png" alt="">

        </div>

    </header>
</template>

<script>
export default {
  name: "Header",
  props: {
    
  },
};
</script>

<style lang="scss" scoped>

    header{

        background-color: #2e3a46;
        width: 100%;
        height: 70px;

        .logo{
            height: 100%;
            width: 140px;
            margin: 0 15px;
            display: flex;
            justify-content: center;
            align-items: center;
            
            

            img{

                width: 100%;

            }

        }

    }

</style>