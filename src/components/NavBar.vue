<template>
  <div class="NavBar">
    <img class="NavBar__logo" src="../assets/ayahuasca.jpeg" alt="ayahuascamed"/>
    <h2>Ayahuascamed</h2>
    <div class="NavBar__language">
      <img v-if="lang == 'en'" class="NavBar__language--flag" src="../assets/Flag_of_the_United_States.svg.webp" @click="changeLangEs()"/>
      <img v-if="lang == 'es'" class="NavBar__language--flag" src="../assets/Flag_of_Colombia.svg.webp" @click="changeLangEn()"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBar",
    data(){
    return {
        lang: ''
    }
  },
  methods:{
    changeLangEs(){
      localStorage.clear();
      localStorage.setItem('language', 'es')
      location.reload();
    },
    changeLangEn(){
      localStorage.clear();
      localStorage.setItem('language', 'en')
      location.reload();
    }
  },
  mounted(){
    this.lang = localStorage.getItem('language');
  }
}
</script>
<style lang="scss">
.NavBar{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    background: #fcfbf9;
    padding: 0px 5px 0px 5px;
    &__logo{
    width:60px;
    border-radius: 50%
    }
    &__language{
      width: 100%;
      &--flag{
        width:40px;
        height:40px;
        margin: 10px 0px 0px 30px;
        border-radius: 50%;
    }
    }
}


</style>