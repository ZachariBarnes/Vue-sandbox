<script setup lang="ts">
defineProps<{
  msg: string;
}>();
</script>

<template>
  <div class="container">
    <div class="top-bar">
      <div class="top-bar-logo"> 
        <img
            alt="Vue logo"
            class="logo"
            src="@/assets/VDL_Logo.png"
            width="80"
            height="80"
        />
        </div>
        <div class="top-bar-title">
        <h1 >{{ msg }}</h1>
        <h4 class="top-bar-by">by Vidulum</h4>
        </div>
    </div>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  /*top: -10px;*/
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,

@media (min-width: 1024px) {
  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}

.logo {
  display: block;
  margin: 0 auto 0rem;
}

.top-bar-logo {
  padding: 1rem 0rem 0rem 1rem;
  float: left;
  align-items: center;
}
.top-bar-by {
  text-align: center;
  top: -10px;
}
.top-bar-title {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
  align-items: center;
  padding: 1rem;
  width: 35.6rem;
}
.top-bar {
  position: sticky;
  top: 0;
  width: 100vw;
  text-align: left;
  align-items: center;
}
.container {
  display: flex;
  justify-content: space-around;
  align-items: flex-start;
  border-bottom: 2px solid hsla(160, 100%, 37%, 1);
  background-color: #131313 !important;
}
</style>
