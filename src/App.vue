<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <!-- <header>
    <div class="w-full bg-green-100 p-0 m-0">
      
    </div>

    <div class="grid grid-flow-col grid-rows-3 gap-4p-4 p-4">
      <div class="row-span-3"><img alt="Vue logo" class="logo" src="@/assets/logo.png" width="125" height="125" /></div>
      <div class="col-span-2 text-black" style="font-weight: bold; ">Sign in to your <br> <span
          style="color: orange; font-weight: bold;">Account</span></div>
      <div class="col-span-2 row-span-2  text-black" style="color: grey; font-weight: normal;">Singn in to your Account
      </div>
    </div>

    <div class="wrapper">
      <HelloWorld msg="Hey bro!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header> -->

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    /* padding-right: calc(var(--section-gap) / 2); */
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
