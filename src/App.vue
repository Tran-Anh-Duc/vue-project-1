<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <header>
    <img
      src="@/assets/logo.svg"
      alt="vue logo"
      class="logo"
      width="60"
      height="60"
    />
    <nav>
      <RouterLink to="/" class="btn-main">
        <div >home </div>
      </RouterLink>
      
      <RouterLink to="/create" class="btn-action">
        <div >create </div>
      </RouterLink>
    </nav>
       
  </header>

<router-view></router-view>

</template>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  padding: 0.4rem 2rem;
  align-items: center;
  box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.15);
  width: 500px;
  height: 150px;
  /* margin: auto;
  position: absolute;
  top: 15%;
  left: 50%;
  transform: translate(-50%, -50%); */
}

nav {
  display: flex;
  column-gap: 1rem;
}

a {
  color: white;
  text-decoration: none;
}
</style>
