<script>
import navbar from './Components/navbar.vue';
export default{
  name: 'app',
  components:{
    navbar
  },
  data(){
    return{
      navlinks: [
        {text: 'Home', href: '#Home'},
        {text: 'About', href: '#About'},
        {text: 'Learnmore', href: '#Learnmore'},
      ]
    }
  }

}
</script>

<template>
  <navbar :links="navlinks" />
  
</template>