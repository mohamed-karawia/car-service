<template>
  <div class="content">
    <content-part v-for="(content, index) in contents" :key="index" :content="content"/>

  </div>
</template>

<script>
import contentPart from './contentPart.vue';

export default {
  components:{
    contentPart
  },
  data(){
    return{
      contents: [
        {icon: 'icon-location', text: 'Found dealer', color: '#2194E0'},
        {icon: 'icon-shopping-bag', text: 'Online order', color: '#1380C7'},
        {icon: 'icon-envelope-open', text: 'Contact Us', color: '#1272B1'},
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
@import "../../sass/global.scss";

.content {
  width: 90%;
  //height: 6rem;
  background-color: black;

  position: absolute;
  left: 50%;
  top: 85%;
  transform: translateX(-50%);

  display: flex;
  justify-content: stretch;

  @media only screen and (max-width: 720px){
    flex-direction: column;
  }

    @media only screen and (max-width: 460px){
    top: 90%;
  }
}
</style>