
<template>
  <div class="main">
    <div class="top">
      <headermoutain></headermoutain>
      <h1 class="top-text">Moutains In The World</h1>
    </div>

    <div class="container">
      <div class="row">
        <div class="moutaincard2 col-12 col-md-4 p-lg-3 mb-5">
          <moutaincardv-2
            :id="moutains[0].id"
            :image="moutains[0].image"
            :name="moutains[0].title"
          ></moutaincardv-2>
        </div>
        <div class="moutaincard2 col-12 col-md-4 p-lg-3 mb-5">
          <moutaincardv-2
            :id="moutains[0].id"
            :image="moutains[0].image"
            :name="moutains[0].title"
          ></moutaincardv-2>
        </div>
        <div class="moutaincard2 col-12 col-md-4 p-lg-3 mb-5">
          <moutaincardv-2
            :id="moutains[0].id"
            :image="moutains[0].image"
            :name="moutains[0].title"
          ></moutaincardv-2>
        </div>
      </div>
    </div>

    <div class="container moutaininfo">
      <div class="row">
        <div class="col-12 col-md-6 p-md-0 mb-5 mb-md-0">
          <img :src="moutains[1].image" alt="" width="100%" height="auto" />
        </div>
        <div class="col-12 col-md-6 p-md-0 mb-5 mb-lg-0">
          <div class="moutaininfo-name">{{ moutains[1].title }}</div>
          <div class="moutaininfo-dct">{{ moutains[1].description }}</div>
          <nuxt-link :to="`/${moutains[1].id}`" class="readmore"
            ><button class="button-readmore">Read more</button></nuxt-link
          >
        </div>
        <div class="col-12 col-md-6 p-md-0 mb-5 mb-md-0">
          <div class="moutaininfo-name">{{ moutains[2].title }}</div>
          <div class="moutaininfo-dct">{{ moutains[2].description }}</div>
          <nuxt-link :to="`/${moutains[2].id}`" class="readmore"
            ><button class="button-readmore">Read more</button></nuxt-link
          >
        </div>
        <div class="col-12 col-md-6 p-md-0 mb-5 mb-lg-0">
          <img :src="moutains[2].image" alt="" width="100%" height="auto" />
        </div>
      </div>
    </div>
    <div class="seemoutain text-center mt-5">See Moutains</div>

    <b-container>
      <div class="row">
        <div
          v-for="m in moutains"
          :key="m.id"
          class="col-12 col-sm-6 col-md-4 mb-3"
        >
          <moutaincard
            :id="m.id"
            :image="m.image"
            :name="m.title"
          ></moutaincard>
        </div>
      </div>
    </b-container>
    <footermoutain></footermoutain>
  </div>
</template>
<script>
import Footermoutain from '~/components/Footermoutain.vue'
import Headermoutain from '~/components/Headermoutain.vue'
import Moutaincard from '~/components/Moutaincard.vue'
import Moutaincardv2 from '~/components/Moutaincardv2.vue'

export default {
  components: { Moutaincard, Moutaincardv2, Headermoutain, Footermoutain },
  async asyncData({ $axios }) {
    const res = await $axios.$get(`https://api.nuxtjs.dev/posts`)
    return {
      moutains: res,
    }
  },
  data() {
    return {
      moutains: null,
    }
  },
}
</script>

<style scoped>
.seemoutain {
  padding: 50px 0px;
  font-size: 60px;
  font-weight: bold;
  color: rgb(49, 49, 49);
}
.moutaininfo-name {
  font-size: 35px;
  font-weight: bold;
  padding: 25px;
  color: rgb(49, 49, 49);
}
.moutaininfo-dct {
  font-size: 20px;
  padding: 0px 25px 25px 25px;
  color: rgb(49, 49, 49);
}
.main {
  margin-bottom: 100px;
}

.banner {
  border-radius: 0px;
  background-image: linear-gradient(rgba(17, 17, 17, 0), rgb(49, 48, 48));
}
.top {
  background-image: linear-gradient(rgba(255, 255, 255, 0), rgb(255, 255, 255)),
    url(https://images.unsplash.com/25/peak.jpg?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80);
  min-height: 60vh;
  background-position: center;
  background-size: cover;
  position: relative;
  width: 100%;
}
.top-text {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 100%;
  padding: 20px 15px;
  text-align: center;
  color: rgb(49, 49, 49);
  font-size: 10vh;
}
.button-readmore {
  background-color: rgb(202, 238, 240);
  padding: 10px 15px;
  font-size: 20px;
  font-weight: 600;
  border: none;
  border-radius: 4px;
  color: rgb(49, 49, 49);
}
.button-readmore:hover {
  color: rgb(26, 26, 26);
  background-color: rgb(184, 232, 235);
}
.readmore {
  padding-left: 25px;
}
</style>