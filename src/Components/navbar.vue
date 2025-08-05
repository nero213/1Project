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
};
</script>

<template>
  <nav class="navbar">
    <mybrand-logo  />
    <ul>
      <li v-for="link in links" :key="link.href">
        <a :href="link.href">{{ link.text }} </a>
      </li>
    </ul>
    <div class="registration">
      <button>Sing up</button>
      <button>log in</button>
    </div>
  </nav>
</template>

<style scoped>
.navbar { 
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgb(28, 8, 15);
  padding: 1rem 2rem;
  color: azure;
}

ul {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: 0;
  padding: 0;
  transition: color 0.3s ease;
}

ul a {
  position: relative; /* this is used as a way to set up position conditioning */
  text-decoration: none;
  color: azure;
}

ul a::before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  background-color: red;
  height: 0.1rem;
  width: 0rem;
  transition: all 0.2s ease-in-out;
}

ul a:hover::before {
  width: 2rem;
}
button {
  all: unset;
  margin-right: 1rem;
}
/* Media query for screen */
@media (max-width: 768px) {
  .navbar {
    flex-direction: column;
    padding: 0.8rem;
  }

  ul {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 0.2rem;
    width: 100%;
    margin-top: 0.5rem;
  }

  .registration {
    display: flex;
    flex-direction: column;
    text-align: center;
    gap: 0.3rem;
  }
  button {
    margin: 0px;
  }
}
</style>
