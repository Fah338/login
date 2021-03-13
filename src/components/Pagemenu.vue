<template>
  <div>
    <div class="mt-4">
      <b-card :img-src="Img" img-alt="Card image" img-left class="mb-3">
        <h1>{{ Name }}</h1>
        <br />
        {{ Engname }}<br />

        {{ title }}<br />
        {{ title1 }}<br />
        <b-button variant="outline-danger" style="margin-top: 60px" @click="buy"
          >{{ price }} Bath</b-button
        >
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    Name: String,
    Engname: String,
    title: String,
    title1: String,
    Img: String,
    price: Number,
    id: Number,
  },
  methods:{
    buy(){
      
    }
  }
};
</script>

<style>
</style>