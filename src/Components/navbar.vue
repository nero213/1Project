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
    <mybrandLogo />
    <ul>
      <li v-for="link in links" :key="link.href">
        <a :href="link.href">{{ link.text }} </a>
      </li>
    </ul>

    <div class="registration">
      <button>Log in</button>
      <button>Sing up</button>
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: rgb(99, 6, 40);
  padding: 1rem;
  color: azure;
}

ul {
  display: flex;
  list-style: none;
  gap: 2rem;
  margin: auto;
  padding-bottom: 4px; /* Space for the line */
  transition: color 0.3s ease;
}

ul a {
  position: relative;
  text-decoration: none;
  color: azure;
}

ul a::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  background-color: red;
  height: 0.1rem;
  width: 0rem;
  transition: all 0.2s ease-in-out;

}

ul a:hover::before{
  width: 2rem;
}
</style>
