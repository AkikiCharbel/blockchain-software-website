<template>
  <div class="content pb-5 py-5" id="4">
    <div class="container text-center mb-5">
      <h1>Q&A</h1>
    </div>
    <div class="container">
      <div class="questions mt-3" @click="faq.isOpen = ! faq.isOpen" v-for="faq in faqList" :key="faq.id">
        <h3 class="py-2 mx-3  mt-2">{{ faq.title }}
        <div class="add-remove">
          <img
               v-if="faq.isOpen"
               src="../assets/add-more.png" alt="">
            <img
                 aria-controls="my-collapsible-1"
                 v-if="!faq.isOpen"
                 src="../assets/remove.png" alt="">
        </div>
        </h3>
        <HeightCollapsible
            transition="height 300ms ease-in-out"
            :isOpen="!faq.isOpen"
            @update="onUpdate"
            id="my-collapsible-1"
        > <p class="roman my-4 px-4">{{faq.paragraph}}</p>
        </HeightCollapsible>
      </div>
    </div>
  </div>
</template>

<script>
import HeightCollapsible from "vue-height-collapsible/vue3";

export default {
  name: "FAQ",
  components: {
    HeightCollapsible,
  },
  data(){
    return{
      status:true,
      isOpen: true,
      collapseState: '',
      faqList:[
        {
          id:0,
          title:'What is an NFT?',
          paragraph: "NFT stands for non-fungible token. A digital asset that is non-fungible cannot be arbitrarily swapped with another, it's one of a kind!",
          isOpen: true,
        },
        {
          id:1,
          title:'How can I get a AMAZING NFT CLUB?',
          paragraph: "The official public sale will be held end of May 2022, the exact date is TBA. Presale will occur 24 hours prior to the public sale, and will only be available to members who are whitelisted.",
          isOpen: true,
        },
        {
          id:2,
          title:'How do I join Presale?',
          paragraph: "You can gain access to our presale by becoming whitelisted. Find out more by checking our Discord Server!",
          isOpen: true,
        },
      ]
    }
  },
  methods:{
    onUpdate({ state }) {
      this.collapseState = state
    },
  }
}
</script>

<style scoped>
.content{
  background-color: #b1b5dc;
  background-size: contain;
  background-position: center;
  font-family: Kango;
}
.roman{
  font-family: Metropolis;
  font-size: 1.2rem;
}
.questions{
  color: #141414;
  position: relative;
  border: 2px solid #141414;
  border-radius: 20px;
  cursor: pointer;
}
.add-remove{
  position: absolute;
  top: 50%;
  transform: translate(-50%,-50%);
  right: -60px;
}

@media (min-width:  1000px) {
  .add-remove {
    right: -180px;
  }
}
h3{
  max-width: 80%;
  position: relative;

}

img{
  cursor: pointer;
  width: 80%;
}

</style>