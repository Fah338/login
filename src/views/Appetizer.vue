<template>
    <div class="Menu">
        <b-carousel
        id="carousel-fade"
        style="text-shadow: 0px 0px 2px #000"
        fade
        indicators
        img-width="100"
        img-height="300"
        >
        <b-carousel-slide
      img-src="https://www.hachiban.co.th/_files/images/full/OJ7FYPM6.jpg"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="https://www.hachiban.co.th/_files/images/full/OEESUK0I.jpg"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="https://www.hachiban.co.th/_files/images/full/RWQJ1E5R.jpg"
    ></b-carousel-slide>
    <b-carousel-slide
      img-src="https://www.hachiban.co.th/_files/images/full/S37MKC6J.jpg"
    ></b-carousel-slide>
    </b-carousel>
    <div class="container">
        <b-nav tabs fill  align="left">
            <router-link to="/Menu">Main coures</router-link>           |
            <router-link to="/Appetizer">Appetizer</router-link>
        </b-nav>
    </div>
  </div>
</template>