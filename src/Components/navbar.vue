<script>
import mybrandLogo from "./mybrandLogo.vue";

export default {
  name: "navbar",
  components: {
    mybrandLogo,
  },
  props: {
    links: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      IsSideNavOpen: false,
    };
  },
  methods: {
    toggleSidenav() {
      this.IsSideNavOpen = !this.IsSideNavOpen;
    },
  },
};
</script>

<template>
  <nav class="navbar">
    <mybrand-logo />
    <button class="hamburger" @click="toggleSidenav">
      <span></span>
      <span></span>
      <span></span>
    </button>
    <ul :class="{ 'sidenav-active': IsSideNavOpen }">
      <li v-for="link in links" :key="link.href">
        <a :href="link.href">{{ link.text }} </a>
      </li>
      <li class="registration-mobile">
        <button>Sign up</button>
        <button>Log in</button>
      </li>
    </ul>
    <div class="registration-desktop">
      <button>Sing up</button>
      <button>Log in</button>
    </div>
  </nav>
</template>

<style scoped>
/* this is the styles for the navbar  */
.navbar {
  display: flex; /* this would make the child to be inline */
  justify-content: space-between; /* the children would now be given a space */
  align-items: center;
  background-color: aqua;
  padding: 3vh;
}
ul {
  display: flex; /* this would make the child to be inline */
  gap: 2vw; /* the vw is means 1% of the view width of the viewport */
  margin: 0;
  padding: 0;
  list-style-type: none; /* this is to remove the bullet points */
}
ul a {
  text-decoration: none; /* this is to remove the underline in the bullter points */
  color: #000000;
  transition: all 0.3s ease-in-out;
  position: relative;
}

ul a::before {
  content: "";
  position: absolute;
  background-color: red;
  width: 0rem;
  height: 0.1rem;
  left: 0;
  bottom: -2px;
  transition: all 0.3s ease-in-out;
}
/* this would add a hover effect to the pseudo class to enable the background color to be red */
ul a:hover::before {
  width: 100%;
}
.registration-desktop {
  display: flex;
  gap: 0.5vw;
}
.registration-desktop button {
  all: unset;
  border: solid 1px;
  padding: 1.5vh 1vw; /* top & bottom = 1.5vh, left & right = 1vw */
  border-radius: 10px;
  transition: all 0.3s ease-in-out;
}
.registration-desktop button:hover {
  transform: scale(1.1);
  cursor: pointer;
}
/* this is to hide the mobile until it reach a certain size */
.registration-mobile {
  display: none;
}
/* this is to hide the humber not unless it get to a certain size */
.hamburger {
  display: none;
}

/* media query to so if the screen reach this size it would apply these style */
@media (max-width: 768px) {
  .registration-desktop {
    display: none;
  }

  ul {
    /* this is just for setting the position */
    position: fixed; /* what this does is that the ul elements is now push to the viewport */
    top: 0;
    left: 0;
    height: 100vh;
    width: 60vw;
    z-index: 1000;

    background-color: red;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    /* hidden mobile side navigation menu */
    transform: translateX(0);
    transition: transform 0.3s ease-in-out;
  }
}
</style>
