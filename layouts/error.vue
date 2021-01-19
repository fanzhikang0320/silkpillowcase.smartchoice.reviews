<template>
  <div class="error-container">

      <div class="error-box">
          <img src="@/assets/image/404.jpg" alt="404" class="error-img">
            <p class="desc">The page you visited does not exist, please return to the home page.</p>

            <nuxt-link to="/" class="btn">Home</nuxt-link>
      </div>
      
  </div>
</template>

<script>
export default {
    layout: 'white'
}
</script>

<style lang="scss" scoped>
.error-container {
    position: relative;
    width: 100%;
    height: 100%;
    background-color: #f8f8f8;

    .error-box {
        position: absolute;
        left: 50%;
        top: 45%;
        transform: translate(-50%,-50%);
        display: flex;
        flex-direction: column;
        align-items: center;
        .desc {
            font-size: 18px;
            margin: 25px 0px;
        }
        .btn {
            @include aToBtn(140px,40px,5px,16px);
            margin-top: 30px;
        }
    }
}
</style>
