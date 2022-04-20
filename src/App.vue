<script setup lang="ts">
import { RouterLink, RouterView } from "vue-router";
// import HelloWorld from "@/components/HelloWorld.vue";
import HeaderComponent from "@/components/HeaderComponent.vue";
import MainComponent from "@/components/MainComponent.vue";
const authorized = true;
</script>

<template>
  <header>
    <div class="wrapper">
      <div class="top-header">
        <HeaderComponent msg="Crypto Transaction Tool" />
      </div>

      <div class="body">
        <MainComponent
          :isAuthorized=authorized
          email-address="Sabin6120@gmail.com"
        />
      </div>
      <!--      <nav>-->
      <!--        <RouterLink to="/">Home</RouterLink>-->
      <!--        <RouterLink to="/about">About</RouterLink>-->
      <!--      </nav>-->
    </div>
  </header>

  <!--  <RouterView />-->
</template>

<style>
@import "@/assets/base.css";

#app {
  background-color: #232228 !important;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  max-height: 100% !important;
  max-width: 100vw !important;
  overflow-x: hidden !important;
  margin: 0 auto;
  /*padding: 2rem;*/

  font-weight: normal;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}
.top-header {
  padding-bottom: 2rem;
  position: sticky;
  top: 0;
}
.body {
  padding: 0vw 4vw;
}
a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
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
  body {
    display: flex;
    place-items: center;
  }

  #app {
    /*display: grid;*/
    /*grid-template-columns: 1fr 1fr;*/
    /*padding: 0 2rem;*/
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
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
