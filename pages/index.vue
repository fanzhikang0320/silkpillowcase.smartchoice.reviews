<template>
  <div class="container">
    <section class="banner-area">

      <div class="banner-container">
        <div class="banner-content">
            <h1 class="g">2020’s TOP {{productList.length - 1}}</h1> 
            <h1 class="a">{{websiteName}}</h1>
        </div>
        <img src="@/assets/image/seal.png" :alt="websiteName" class="seal">
      </div>
    </section>
    <div class="main-container">

      <section class="website-desc-area">
        <h2 class="area-title">The Best {{websiteName}} In 2020</h2>
        <div class="content area-content">
          <p>No matter what position you sleep in, you spend hours each night with your hair or face pressed up against a pillow. Your pillowcases get covered with dead skin cells, oils from your skin, saliva, sweat and all sorts of other bacteria, making them a dust mite breeding and feeding playground. This can make for a dust mite paradise.</p>
          <p>We  has tested dozens of real silk and synthetic satin pillowcases for durability, moisture wicking properties, smoothness, and more. We also send them home with our consumer panel for real life snooze-testing.</p>
        </div>
      </section>

      <section class="product-area">
        <p class="desc">And then we sorted out {{productList.length - 1}} major options:</p>
        <div class="product-list-container">
          <div :class="{'product-item': true, 'first-item': index == 0, 'last-item': index == productList.length - 1}" v-for="(product,index) in productList" :key="index">
            <div class="circle" v-if="index != productList.length- 1">
                <span class="num">{{index + 1}}</span>
            </div>
            <div class="corner-box" v-if="index == 0">
                <span class="text">Editor's Choice</span>
            </div>
            <div class="big-title" v-if="index == productList.length - 1">The Most Popular {{websiteName}} In 2020</div>
            <div class="product-link-box" @click="jump(product.link)">
              <div class="product-container">
                  <div class="product-container-left">
                      <div class="picture-box">
                          <img :src="product.picture" :alt="product.name" class="picture">
                      </div>
                      <div class="desc-list-box">
                          <h2 class="product-name">{{product.name}}</h2>
                          <ul class="list-box" v-if="product.strengthList.length != 0">
                              <li v-for="(item,id) in product.strengthList" :key="id">
                                  <span class="icon"></span>
                                  <p class="text">{{item.text}}</p>
                              </li>
                          </ul>
                          <ul class="list-box weakness-list" v-if="product.weaknessList.length != 0">
                              <li v-for="(item,id) in product.weaknessList" :key="id">
                                  <span class="icon"></span>
                                  <p class="text">{{item.text}}</p>
                              </li>
                          </ul>
                          <p class="buys" v-if="index == 0 || index == productList.length - 1">55% Discount Now</p>
                      </div>
                  </div>
                  <div class="product-container-right">
                      <p class="good">
                          <span class="text">{{index == 0 || index == productList.length - 1 ? 'Excellent': index == 1 ? 'Very Good': 'Good'}}</span>
                          <span class="king-icon" v-if="index == 0 || index == productList.length - 1"></span>
                          <span class="good-icon" v-if="index == 1"></span>
                      </p>
                      <p class="rate-box"><span class="score">{{product.score}}</span><span>/10</span></p>
                      <a :href="product.link" target="_blank" class="btn">
                          <span class="text">Visit Site</span>
                          <span class="icon"></span>
                      </a>
                  </div>
              </div>
            </div>
        </div>
        </div>
      </section>

      <section class="why-choose-area">
        <h2 class="area-title">Why choose silk pillowcase?</h2>
        <img src="/data/img/blissy-poster.jpg" alt="Blissy" class="blissy-poster">
        <div class="content area-content">
          <p>Believe it or not, the Hollywood “it crowd” and beauty industry professionals have known about the anti-aging silk pillowcase secret for a while now. It makes perfect sense when you realize that all of your expensive anti-aging cream product is going to waste when you lie down on your regular cotton pillowcase at night. You carefully apply the product to your face and neck, and then proceed to get into bed, put your face on a highly absorbent cotton surface, and toss and turn all night long.</p>

          <p>No wonder your anti-aging products aren’t delivering the results you expected. They need time to set in and work their magic undisturbed! Blissy’s silk surface is absorption-resistant and reduces facial friction by 43% -- a massive difference compared to cotton pillowcases.</p>
        </div>
      </section>
      <section class="why-area">
        <h2 class="area-title">Why choose Blissy Silk Pillowcase?</h2>
        <div class="content-item">
          <h5 class="title">Better & Cooler Sleep</h5>
          <div class="area-content">
            <p>The temperature regulating properties of the silk pillowcase allow you to keep cool at all times during the night without the discomfort associated with fluctuating temperature and the constant tossing and turning for a restful night sleep.</p>
          </div>
        </div>
        <div class="content-item">
          <h5 class="title">Goodbye Allergies</h5>
          <div class="area-content">
            <p>Chalk up another win for silk when it comes to allergies. While cotton is a veritable breeding ground for allergens, silk is totally hypoallergenic -- which means you can start waking up with clearer sinuses, dry eyes, and easy breathing. If you have sensitive skin, you’ll also notice less redness, puffiness, and blemishes when sleeping on a hypoallergenic surface like silk.</p>
          </div>
        </div>
        <div class="content-item">
          <h5 class="title">No More Hair Damage</h5>
          <div class="area-content">
            <p>Industry-leading hair stylists have also known for some time now that silk pillowcases are the only way to sleep. As you toss and turn at night, your hair is being scraped and dragged along a cotton surface that’s actually rougher under a microscope than you think. The result? Split ends, dull hair, and a tousled mess when you wake up in the morning.</p>
          </div>
        </div>
        <div class="content-item">
          <h5 class="title">Clearer Skin</h5>
          <div class="area-content">
            <p>Generally speaking, moisturized skin is healthy skin… and dry skin leads to all sorts of blemish and wrinkle-causing conditions. Perhaps the biggest advantage of all when you switch to Blissy is the facial moisture retention you’ll enjoy. No more wiping all that important lotion directly into a cotton pillowcase that soaks it up like a sponge. Let your skincare products do the job they were meant to do by treating yourself to a silky sleep session, every night!</p>
          </div>
        </div>
      </section>
      <section class="special-offer-area">
        <h3 class="offer">Special Offer on Now!</h3>
        <p class="sub">Now there is a special offer, but such a low price, there may not be much left! </p>
        <p class="sub">So do it now!</p>

        <div class="posters-box">
          <img src="/data/img/poster.jpg" :alt="websiteName" class="picture">
          <a :href="mainLink" target="_blank" rel="noopener noreferrer nofollow" class="btn">
              <span>I want better sleep,skin and hair Today!</span>
              <span class="icon"></span>
          </a>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ app, redirect }) {

    try {
      const res = await app.$axios.$get('/data/product.json');
      const baseScore = res.baseScore;
      // 如果数组为0
      if (res.data.length == 0) {
        redirect('/error');
      }
      res.data.forEach((item,index) => {
        if (baseScore[index] == undefined) {
          item.score = String(Number(baseScore[index - 1]) - 0.2);
        } else {
          item.score = baseScore[index];
        }
      })

      res.data.push(res.data[0]);
      return { 
        mainLink: res.data[0].link,
        websiteName: res.websiteName,
        productList: res.data
      }
    } catch (error) {
      redirect('error');
    }

    
  },
  data() {

  },
  methods: {
    jump(url) {
      window.open(url);
    }
  }
}
</script>

<style lang="scss" scoped>
@import '~/assets/scss/index.scss';
</style>