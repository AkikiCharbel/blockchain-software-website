<template>
  <div class="content">
    <div class="container">
      <nav :class="{change_color: scrollPosition > 50}" class="navbar navbar-expand-lg fixed-top container-fluid mobile-color">
        <div class="container-fluid ">
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav ms-auto mb-2 mb-lg-0 d-flex justify-content-center align-items-center">
              <li class="nav-item">
                <a class="nav-link" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" @click="scroll(1)">MINT</a>
              </li>
              <li class="nav-item">
                <a class="nav-link"  data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" @click="scroll(2)">ROADMAP</a>
              </li>
              <li class="nav-item">
                <a class="nav-link"  data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" @click="scroll(3)">TEAM</a>
              </li>
              <li class="nav-item">
                <a class="nav-link"  data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" @click="scroll(4)">FAQ</a>
              </li>
            </ul>
          </div>
        </div>
      </nav>
    </div>
    
    <div class="container text-center header-middle-content">
      <h1>Mint your fav NFT</h1>
      <button class="join-discord-btn py-2 px-4">
        <a href="https://idyllic-dolphin-cc67b7.netlify.app/">
          GO MINT
        </a>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "header",
  data(){
    return{
      scrollPosition: null,
      show:true
    };
  },
  components:{
  },
  methods:{
    scroll(id) {
      document.getElementById(id).scrollIntoView({
        behavior: "smooth"
      });
      this.show =!this.show;
    },
    updateScroll() {
      this.scrollPosition = window.scrollY
    }

  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  }
}
</script>

<style scoped>
.content{
background-image: url("../assets/giphy (1).gif");
  background-position: center;
  background-size: cover  ;
  background-repeat: no-repeat;
  height: 991px;
  color:#141414 ;
  font-family: Kango;
  position: relative;
  overflow-x: hidden;
}
@media (min-width: 900px) {
  .navbar {
    padding: 10px 250px;
  }
}


@media (max-width: 900px){
  .navbar-image{
    width: 190px;
  }
}
.nav-item a{
  font-family: Kango;
  color: white;
  font-size: 1.4rem;
  cursor: pointer;
}


.navbar-toggler-icon {
  background-image: url(
  "data:image/svg+xml;charset=utf8,%3Csvg viewBox='0 0 32 32' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath stroke='rgba(20,20,20)' stroke-width='2' stroke-linecap='round' stroke-miterlimit='10' d='M4 8h24M4 16h24M4 24h24'/%3E%3C/svg%3E");
}
.navbar-toggler:focus {
  box-shadow: none;
}
.header-middle-content{
  margin-top: 200px;
}

h1{
  font-size: 4rem;
  color: white;
}
@media (max-width: 900px) {
  h1{
    font-size: 2em;
  }
  .header-middle-content{
    margin-top: 230px;
  }
}

.join-discord-btn{
  color: orange;
  font-weight: bolder;
  background-color: white;
  border: none;
  border-radius: 10px;
  height: 50px;
}



.join-discord-btn:hover {
  color: white;
  background-color: orange;
  transition: 0.2s;
}
.curved-bottom img{
  width: 100vw;

  }

@media (max-width: 900px) {
  .parachute{
    top: -99px;
    right: 0px;
  }
  .parachute img{
    width: 150px;
  }
}

.change_color{
  background-color: #8e98f3;
  transition: 0.5s;
}
a:link, a:visited {
  color: #fdd21e;
}

a:hover, a:active {
  color: #fdd21e;
}

</style>
