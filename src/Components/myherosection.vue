<script>
import Tonkatsu from "../assets/Tonkatsu.jpg";
import testing from "../assets/tonkatsu2.jpg";
import logo from "../assets/tonkatsu3.jpg";
export default {
  name: "herosection",
  data() {
    return {
      Tonkatsu, // this is for the image
      testing, // this for the image
      logo, // this is for the image
      Image: [Tonkatsu, testing, logo], // created an array to store the image
      CurrentIndex: 0, // create a variable to be inserted in the array to get the image index
      show: false,
    };
  },
  mounted() {
    // seInterval would apply the image slider a 2000 or 2 seconds
    // start at 0 and then using a % operator it reset back to zero
    // creating a loop
    setInterval(() => {
      this.CurrentIndex = (this.CurrentIndex + 1) % this.Image.length;
    }, 2000);
  },
};
</script>

<template>
  <div class="container">
    <div class="Imgcontiner">
      <transition name="fade" mode="out-in">
        <img
          :src="Image[CurrentIndex]"
          :key="Image[CurrentIndex]"
          alt="slideshow"
        />
      </transition>
    </div>

    <div class="HeroText">
      <h1>Welcome to the Daniela Tonkatsu - Where tradition meets flavor.</h1>
      <p>
        Crispy, golden pork cutlets made fresh with authentic Japanese flavors.
        Comfort food done right — dine in or order online today.
      </p>

      <div class="testing">
        <button>testing</button>
        <button>testing</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: row-reverse; /* reverses order: text left, image right */
  align-items: center; /* optional: vertically center */
  /* spacing between image and text */
  margin: 2rem 3rem; /* the 2rem = is from top to bottom and 3rem = is right to left */
}

.Imgcontiner {
  display: flex;
  height: 70vh; /* make it larger so it’s visible */
  width: 50%;
  align-items: center;
  justify-content: center;
}
.fade-enter-active,
.fade-leave-active {
  transition: all 0.5s ease-in-out;
}
.fade-enter-from {
  transform: scale(1.1);
  opacity: 0;
}
.fade-leave-to {
  opacity: 0;
}

.Imgcontiner img {
  height: 60vh;
  overflow: hidden;
  border-radius: 15vh;
  transition: all 0.5s ease-in-out; /* smooth fade effect */
}
.HeroText {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 70vh;

  width: 50%;
}
.HeroText p {
  text-align: left;
  font-size: 1rem;
}
.HeroText h1 {
  font-weight: bold;
  text-align: center;
  font-size: 40px;
  margin-bottom: 6vh;
  padding-top: 8vh;
}
/* this is for the buttons */
.testing {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  width: 100%;
  gap: 8px;

}
.testing button {
  all: unset;
  border: solid black;
  padding: 0.5rem 2rem;
  border-radius: 20px;
  transition: all 0.3s ease-in-out;
}
.testing button:hover {
  transform: scale(1.05);
}
.testing button:first-child {
  background-color: red;
}
/* using media query for the phones  */
@media (max-width: 1064px) {
  .Imgcontiner img {
    display: none; /* this is used to hide the image once reach a certain size */
  }
  .container {
    height: 45vh;
    display: flex;
    align-items: flex-start;
    margin: 10px 20px;
    
  }
  .HeroText {
    height: 0;
    display: flex;

    width: 100%;
  }
  .HeroText h1 {
    /* this goes from top,right,bottom,left */
    margin: 0px 0px 10px 0px;
    font-size: 2rem;
    animation-iteration-count: infinite;
    animation-duration: 1s;
    animation-name: textspin;
  }
  .HeroText p {
    text-align: center;
  }
  .Imgcontiner {
    width: 0; /* this is to remove the div */
  }
  @keyframes textspin {
    0%,
    100% {
      transform: translateY(0); /* start and end at rest */
    }
    50% {
      transform: translateY(-15px); /* float upward */
    }
    
  }
}
</style>
