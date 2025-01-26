<script setup>

import { computed, onMounted, ref } from 'vue';
import { useRouter } from 'vue-router';

const users =ref([]);
const txtSearch = ref('');
const router =useRouter();
///cach1
// onMounted ( () => {
  
//   fetch('https://jsonplaceholder.typicode.com/users')
//       .then(response => response.json())
//       .then(json => users.value =json)
// })


///cach2
onMounted ( () => {
    ( async () => {
        const res = await fetch('https://jsonplaceholder.typicode.com/users')
        const data =await res.json();
        users.value = data;
    })()  

})


const filterUser = computed( () => {
    
    return users.value.filter(item => item.name.toUpperCase().indexOf(txtSearch.value.toUpperCase()) !== -1 )
})

</script>
<template>
  <main style="color: white; padding: 2rem">
    <input type="text" placeholder="Emter search here!!!" v-model="txtSearch" />
    <div class="group-card">
      <div class="card-item" v-for="user in filterUser">
          <div @click="router.push({path:`/todo/${ user?.id }`})">
            <h2 style="color: black;">{{ user.name }}</h2>
            <i>{{ user.email }}</i>
          </div>
      </div>
    </div>
  </main>
</template>

<style>


</style>
