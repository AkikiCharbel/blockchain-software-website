<template>
<div>
  <div class="roadmap py-5 text-center" id="2">
    <div class="container px-4">
      <h1 class="text-center pt-5">ROADMAP 2022</h1>

      <div id="timeline" :style="styleObject">
        <div class="airplane" :style="airplaneObject">
          <img src="../assets/airplane-illustration.svg" alt="">
        </div>
        <div class="timeline-item "
             data-aos-once="true">
          <div class="timeline-icon ">
            <img src="../assets/timeline-blue-circle.png" alt="">

          </div>
          <div class="timeline-content mb-5">
            <h2>
              <span class="text-orange">10%</span>
              first step</h2>
            <p>
             Lorem ipsum dolor sit amet, consectetur adipisicing elit. Architecto beatae in ipsum nisi rem velit voluptatem voluptatibus! Accusantium autem dignissimos esse laboriosam nesciunt possimus voluptates.
            </p>

          </div>

        </div>

        <div class="timeline-item" data-aos="fade-left">
          <div class="timeline-icon">
            <img src="../assets/timeline-blue-circle.png" alt="">

          </div>
          <div class="timeline-content right mb-5">
            <h2>
              <span class="text-orange">20%</span>

              Second</h2>
            <p>
             Lorem ipsum dolor sit amet, consectetur adipisicing elit. Corporis delectus dolorem ducimus enim facere fugit ipsa maxime minima nam nulla numquam officia suscipit, tempora ullam!
            </p>
          </div>

        </div>

        <div class="timeline-item" data-aos="fade-right" data-aos-offset="300">
          <div class="timeline-icon">
            <img src="../assets/timeline-blue-circle.png" alt="">

          </div>
          <div class="timeline-content mb-5">
            <h2>
              <span class="text-orange">30%</span>

              Third step</h2>
            <p>
             Lorem ipsum dolor sit amet, consectetur adipisicing elit. Sint, vitae!
            </p>
          </div>

        </div>

        <div class="timeline-item" data-aos="fade-left" data-aos-offset="300">
          <div class="timeline-icon">
            <img src="../assets/timeline-blue-circle.png" alt="">

          </div>
          <div class="timeline-content right mb-5">
            <h2>
              <span class="text-orange">40%</span>

              Last Step</h2>
            <p>
              Lorem ipsum dolor sit amet, consectetur adipisicing elit. Doloribus molestiae praesentium quibusdam. Nostrum rerum, tenetur!           </p>
          </div>

        </div>

        <div class="timeline-item" data-aos="fade-right" data-aos-offset="300">
          <div class="timeline-icon">
            <img src="../assets/timeline-blue-circle.png" alt="">

          </div>

      </div>
    </div>
  </div>
  </div>
</div>
</template>

<script>

export default {
  data(){
    return{
      styleObject:{
        '--height':'10%',
      },
      airplaneObject:{
        '--top' :'10%'
      }
    };
  },
  components:{
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const currentScrollPosition = window.pageYOffset;
      let elementID = 2;
      const elementOffsetTop = document.getElementById(elementID).offsetTop
      let timelineHeight = document.getElementById(elementID).offsetHeight;

      if ( currentScrollPosition > elementOffsetTop){
        let percentage = ((currentScrollPosition - elementOffsetTop) / timelineHeight) * 100;
        percentage = percentage + 12 ; // We added a 10% offset

        if(percentage <= 100){
          this.styleObject["--height"] = percentage + "%" ;
          this.airplaneObject["--top"] = percentage + "%";
        }
      }
    },
  },
}
</script>

<style scoped>

.roadmap{
  /*background-image:  url("../assets/PNG/BG 3.png") ;*/
  background-color: #b1b5dc;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  margin-top: -40px;
  position: relative;
}
</style>
<style lang="scss" scoped>
@import "https://fonts.googleapis.com/css?family=Dosis:300,400,500,600,700";

// Variables
$bg-body: #f9f9f9;

$red: #ee4d4d;
$blue: #2b2e48;
$primary-color: red;
$secondary-color: $blue;


// Typography
$base-font: helvetica, arial, tahoma, verdana;
$base-font-title: "Dosis", arial, tahoma, verdana;

$base-font-color: #726f77;

// Timeline
$timeline-color: $primary-color;


// Mixins and Placeholders
%clearfix {
  &:after, &:before {
    content: '';
    display: block;
    width: 100%;
    clear: both;
  }
}

@mixin prefix($prop, $val) {
  @each $prefix in '-webkit-', '-moz-', '-ms-', '' {
    #{$prefix}#{$prop}: $val;
  }
}
*, *:before, *:after {
  box-sizing: border-box;
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
}

body, html {
  height: 100%;
}
body {
  background: $bg-body;
  background-size: cover;
  margin: 0;
  padding: 0;
  font-family: $base-font;
  line-height: 20px;
  font-size: 14px;
  color: $base-font-color;
}

img {max-width: 100%;}

a {
  text-decoration: none;
}

.container {
  max-width: 1100px;
  margin: 0 auto;
}

h1,h2, h3, h4 {
  font:{
    family: Kango;
    weight: 500;
  }
  color: #141414;
}

p{
  color: #141414;
  font-family: Metropolis;
}
.project-name {
  text-align: center;
  padding: 10px 0;
}

// Header
header {
  background: $secondary-color;
  padding: 10px;
  @include prefix(box-shadow, 0 3px 3px rgba(0,0,0,0.05));
  @extend %clearfix;

  .logo {
    color: $primary-color;
    float: left;
    font:{
      family: $base-font-title;
      size: 22px;
      weight: 500;
    }

    > span {
      color: lighten($primary-color, 20%);
      font-weight: 300;
    }
  }

  .social {
    float: right;
    .btn {
      font-family: "Dosis";
      font-size: 14px;
      margin: 10px 5px;
    }
  }
}


// Timeline
#timeline {
  width: 100%;
  margin: 30px auto;
  position: relative;
  padding: 0 10px;
  @include prefix(transition, all .4s ease);

  &:before {
    content:"";
    width: 4px;
    height: var(--height);
    background: $timeline-color;
    left: 50%;
    top: 0;
    position: absolute;
  }

  &:after {
    content: "";
    clear: both;
    display: table;
    width: 100%;
  }

  .timeline-item {
    margin-bottom: 50px;
    position: relative;
    @extend %clearfix;

    .timeline-icon {
      width: 179px;
      height: 180px;
      position: absolute;
      top: 18px;
      left: 50%;
      overflow: hidden;
      margin-left: -87px;
      border-radius: 50%;
      border-radius: 50%;
      @include prefix(border-radius, 50%);

      svg {
        position: relative;
        top: 14px;
        left: 14px;
      }
    }

    .timeline-content {
      width: 43%;
      padding: 20px;
      @include prefix(border-radius, 5px);
      @include prefix(transition, all .3s ease);



      &:before {
        position: absolute;
        left: 43%;
        top: 20px;
        width: 0;
        height: 0;
        border-top: 7px solid transparent;
        border-bottom: 7px solid transparent;
        border-left:7px solid $timeline-color;
      }

      &.right {
        float: right;

        &:before {
          right: 43%;
          left: inherit;
          border-left: 0;
          border-right: 7px solid $timeline-color;
        }
      }
    }
  }
}
@media (max-width: 900px) {
  #timeline .timeline-item .timeline-content{
    padding: 0px;
  }
}
// Buttons
.btn {
  padding: 5px 15px;
  text-decoration: none;
  background: transparent;
  border: 2px solid lighten($primary-color, 10%);
  color: lighten($primary-color, 10%);
  display: inline-block;
  position: relative;
  text-transform: uppercase;
  font-size: 12px;
  @include prefix(border-radius, 5px);
  @include prefix(transition, background .3s ease);
  @include prefix(box-shadow, 2px 2px 0 lighten($primary-color, 10%));

  &:hover {
    box-shadow: none ;
    top: 2px;
    left: 2px;
    @include prefix(box-shadow, 2px 2px 0 transparent);
  }
}

@media screen and (max-width: 768px) {
  #timeline {
    margin: 30px;
    padding: 0px;
    width: 90%;
    &:before {
      left: 0;
    }

    .timeline-item {
      .timeline-content {
        width:90%;
        margin-top: 17px;
        float: right;

        &:before, &.right:before {
          left: 10%;
          margin-left: -6px;
          border-left: 0;
          border-right: 7px solid $timeline-color;
        }
      }

      .timeline-icon {
        left: 0;
      }
    }
  }
}
.percentage{
  width: 25px;
}
.marquee{
  color: #F0D712;
  font-size: 40px;
  font-family: Kango;
  border-top: 2px solid #141414;
  border-bottom: 2px solid  #141414;
}
.airplane{
  position: absolute;
  top: var(--top) ;
  left: 50%;
  transform: translate(-46%,-50%);
}
@media(max-width: 900px){
  .airplane{
    left: 0%;
  }
  #timeline .timeline-item{
    margin-bottom: 150px;
  }
}
.car{
  position: absolute;
  bottom: -10px;
  right: 0px;
}
@media (max-width: 900px) {
  .car{
    width: 80px;
  }
}
.illustration{
  position: absolute;
  top: 50px;
  right: 150px;
  width: 150px;
}
@media (max-width: 900px) {
  .illustration{
    top: 86%;
    width: 82px;
    right: 100px;
  }
}
.illustration-right{
  position: absolute;
  top: 50px;
  left: 150px;
  width: 150px;
}
@media (max-width: 900px) {
  .illustration-right{
    top: 90%;
    width: 82px;
    right: 78px;
    left: 119px;
  }
}
.text-orange{
  color: blue;
  font-size: 1.2rem;
  padding-bottom: 10px;
}
</style>