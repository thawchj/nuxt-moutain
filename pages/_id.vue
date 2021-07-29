<template>
  <div>
    <headermoutain></headermoutain>
    <b-jumbotron class="text-center jumbotron">
      <h1 class="text-jumbotron">{{ moutain.title }}</h1>
    </b-jumbotron>
    <div class="container moutainid-body">
      <div class="row">
        <div class="col-12 col-md-4 p-0">
          <img :src="moutain.image" width="100%" />
        </div>
        <div class="col-12 col-md-8 info-moutain">
          <div class="info-text">
            <span class="section-info">Continent: </span>{{ moutain.continent }}
          </div>
          <div class="info-text">
            <span class="section-info">Height: </span>{{ moutain.height }}
          </div>
          <div class="info-text">
            <span class="section-info">Countries: </span
            ><span
              v-for="m in moutain.countries"
              :key="m.length"
              class="countries-style"
              >{{ m }}</span
            >
          </div>
          <div class="info-text-dct">{{ moutain.description }}</div>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-4 offset-lg-4 col-12 mt-5">
          <nuxt-link :to="'/'" class="button-back">
            <button class="w-100 py-3 my-3 buttonback">Back</button>
          </nuxt-link>
        </div>
      </div>
    </div>
    <footermoutain></footermoutain>
  </div>
</template>

<script>
import Footermoutain from '~/components/Footermoutain.vue'
import Headermoutain from '~/components/Headermoutain.vue'
export default {
  components: { Headermoutain, Footermoutain },
  async asyncData({ $axios, route }) {
    const res = await $axios.$get(
      `https://api.nuxtjs.dev/posts/${route.params.id}`
    )
    return {
      moutain: res,
    }
  },
  data() {
    return {
      moutain: null,
    }
  },
}
</script>

<style scoped>
.jumbotron{
    background-color: rgb(202, 238, 240);
    border-radius: 0 ;
}
.text-jumbotron{
    font-size: 10vh;
    font-weight: bold;
    color: rgb(49, 49, 49);
}

.section-info {
  font-size: 22px;
  font-weight: 500;
  color: rgb(49, 49, 49);
}
.info-text {
  font-size: 20px;
  color: rgb(49, 49, 49);
}
.info-text-dct {
  font-size: 18px;
  color: rgb(49, 49, 49);
}

.button-back {
  width: 100%;
}
.info-moutain {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 20px;
}
.countries-style {
  padding: 10px;
}
.buttonback {
  background-color: rgb(202, 238, 240);
  padding: 10px 0px;
  font-size: 20px;
  font-weight: 600;
  border: none;
  border-radius: 4px;
  color: rgb(49, 49, 49);
}
.buttonback:hover {
  color: rgb(26, 26, 26);
  background-color: rgb(184, 232, 235);
}
</style>