<template>
  <div class="brand">
    <img :src="Logoimage" alt="my brand logo" />
    <p>Daniela's tonkatsu </p>
  </div>
</template>

<script>
import Logoimage from "../assets/testing.svg";
export default {
  name: "logo",
  data() {
    return {
      Logoimage,
    };
  },
};
</script>

<style scoped>
.brand{
    display: flex;
    align-items: center;
    justify-content: center;
   

}
.brand img{
    height: 2rem;
    justify-self: center;
  

}
</style>
