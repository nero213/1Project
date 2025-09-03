<script>
import Tonkatsu from "../assets/Tonkatsu.jpg";
import testing from "../assets/tonkatsu2.jpg";
import logo from "../assets/tonkatsu3.jpg";

export default {
  name: "Testing",
  data() {
    return {
      overlay: false,
      image: [
        {
          src: Tonkatsu,
          alt: "Tonkatsu 1",
          title: "testing",
          Description:
            "A golden-brown, crispy Japanese pork cutlet served fresh from the fryer—juicy on the inside, perfectly crunchy on the outside, and bursting with savory flavor.",
        },
        {
          src: testing,
          alt: "Tonkatsu 2",
          title: "testing",
          Description:
            "A golden-brown, crispy Japanese pork cutlet served fresh from the fryer—juicy on the inside, perfectly crunchy on the outside, and bursting with savory flavor.",
        },
        {
          src: logo,
          alt: "Tonkatsu 3",
          title: "testing",
          Description:
            "A golden-brown, crispy Japanese pork cutlet served fresh from the fryer—juicy on the inside, perfectly crunchy on the outside, and bursting with savory flavor.",
        },
        {
          src: logo,
          alt: "Tonkatsu 3",
          title: "testing",
          Description:
            "A golden-brown, crispy Japanese pork cutlet served fresh from the fryer—juicy on the inside, perfectly crunchy on the outside, and bursting with savory flavor.",
        },
        {
          src: logo,
          alt: "Tonkatsu 3",
          title: "testing",
          Description:
            "A golden-brown, crispy Japanese pork cutlet served fresh from the fryer—juicy on the inside, perfectly crunchy on the outside, and bursting with savory flavor.",
        },
        {
          src: logo,
          alt: "Tonkatsu 3",
          title: "testing",
          Description:
            "A golden-brown, crispy Japanese pork cutlet served fresh from the fryer—juicy on the inside, perfectly crunchy on the outside, and bursting with savory flavor.",
        },
      ],
    };
  },
};
</script>

<template>
  <div class="Container">
    <div
      class="ImageDescription"
      v-for="(img, index) in image"
      :key="index"
      @click="this.overlay = !this.overlay"
    >
      <h1>{{ img.title }}</h1>
      <img :src="img.src" :alt="img.alt" />
      <p>{{ img.Description }}</p>
    </div>
  </div>
</template>

<style scoped>
.Container {
  display: flex;
  gap: 20px;
  justify-content: center;
  align-items: flex-start;
  margin: 1rem 3rem;
  flex-wrap: wrap;
}
.Container img {
  height: 30vh;
}
.ImageDescription {
  display: flex;
  border-radius: 15px;
  width: 60vh;
  flex-direction: column;
  justify-content: space-evenly;
  height: 80vh;
  flex-wrap: wrap;
  box-shadow: 1px 0px 10px #8888889b, -1px 0px 10px #8888889b;
  position: relative;
  transition: all 0.3s ease-in-out;
}

.ImageDescription:hover {
  transform: scale(1.02);
}
.ImageDescription h1 {
  text-align: center;
}

.ImageDescription img {
  margin: 10px;
  padding: 10px;
  border-radius: 30px;
}
.ImageDescription p {
  margin: 10px;
  padding: 1.3rem;
  text-align: center;
}
</style>
