<script setup>
import { useRoute } from 'vue-router';
import {onMounted,ref} from 'vue';



const router = useRoute();
const user = ref(null);


onMounted ( () => {
    ( async () => {
        const res = await fetch(`https://jsonplaceholder.typicode.com/users/${router.params.id}`)
        const data =await res.json();
        user.value = data;
    })()  

})

</script>

<template>
  <main style="color: #000; padding: 2rem;margin-top: -7%;">
      <!-- to do item {{ router.params.id }} -->

      <div class="card-item">
          <h2>{{user?.email}}</h2>
          <h3>{{user?.name}}</h3>
          <h2>{{user?.phone}}</h2>
          <h2>{{user?.username}}</h2>
          <h2>{{user?.website}}</h2>
          <div>Delete</div>
      </div>
  </main>
</template>

