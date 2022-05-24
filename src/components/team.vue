<template>
  <div  class="py-5 bg" id="3">
    <div  class="container py-5">
      <h1 class="title text-center mb-5">Our Team</h1>
      <div id="app">
        <carousel :settings="settings" :breakpoints="breakpoints">
          <slide v-for="slide in list" :key="slide">
            <div class="carousel__item text-center py-4 my-3">
              <div class="image-cropper mx-auto mb-4">
                <img class="team-image mb-4" v-bind:src=" require('../assets/'+slide.src1 )">
              </div>
              <h3 class="name">{{slide.name}}</h3>
              <h5 class="role">{{slide.jobtype}}</h5>
            </div>
          </slide>

          <template #addons>
            <navigation />
          </template>
        </carousel>
      </div>
    </div>
  </div>
</template>

<script>
import  '../carousel.css';
import {Carousel, Slide,Navigation} from 'vue3-carousel';

export default {
  name: "Team",
  components: {
    Carousel,
    Slide,
    Navigation
  },
  data() {
    return {
      list: [
        {
          name: 'Marc El Hajjar',
          src1: 'team-default-image.png',
          jobtype: 'Founder',

        },

        {
          name: 'Elias Al Kallasy',
          src1: 'team-default-image.png',
          jobtype: 'Co-Founder',

        },

        {
          name: 'Ray Doueihy',
          src1: 'team-default-image.png',
          jobtype: 'Chief Editor',
        },

      ],
      settings: {
        itemsToShow: 1,
        snapAlign: "center"
      },
      // breakpoints are mobile first
      // any settings not specified will fallback to the carousel settings
      breakpoints: {
        // 700px and up
        700: {
          itemsToShow: 3.5,
          snapAlign: "center"
        },
        // 1024 and up
        1024: {
          itemsToShow: 3,
          snapAlign: "start"
        }
      }
    };
  }

}
</script>

<style scoped>
h3 ,h6{
  font-family: "Product Sans";
  color: white;
}

.title{
  font-family: Kango;
  color: #141414;
}
.bg {
  background-color: #8e98f3;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

}

h5 {
  font-family: Simpsonfont;
}
.name{
  color: #141414;
  font-family: Kango;
}
.role{
  color: #141414;
  font-family: Metropolis;
}
.sociallink{
  color: #1E366B;
}
.carousel__item {
  min-height: 300px;
  width: 100%;
  background-color: #FFFFFF;
  color: white;
  font-size: 20px;
  border-radius: 8px;
  justify-content: center;
  align-items: center;
  border: 3px solid #141414;
}

.carousel__item {
  position: relative;
  top: 0;
  transition: top ease 0.5s;
}

.carousel__slide--visible {
   transform: rotateY(0);
}
@media (min-width: 900px){
  .carousel__item:hover {
    top: -10px;
  }

}
* {
  overflow-x: hidden;
  overflow-y: hidden;
}
.image-cropper {
  width: 130px;
  height: 130px;
  position: relative;
  overflow: hidden;
  border-radius: 50%;
}

img {
  display: inline;
  margin: 1px -33px;
  height: 100%;
  width: auto;
}
</style>