<script setup>
import { reactive, ref } from 'vue';




  // const email =ref('');
  // const name =ref('');
  // const phone =ref('');
  // const website =ref('');


  const todoData =reactive({
    email: '',
    name : '',
    phone: '',
    website: '',
  });


  const handleCreateNewData = async ()=> {
      console.log(todoData);
      
  }


</script>

<template>
  <main style="color: #000; padding: 2rem;margin-top: -7%;">
    <div style="font-weight: bold;">
      Create todo
    </div>
    <div style="margin-top: 2rem;">
      <label >Emal</label>
      <input type="text" placeholder="Emter Emal" v-model="todoData.email" />
    </div>
    <div style="margin-top: 2rem;">
      <label >Name</label>
      <input type="text" placeholder="Emter Name" v-model="todoData.name" />
    </div>
    <div style="margin-top: 2rem;">
      <label >Phone</label>
      <input type="text" placeholder="Emter phone" v-model="todoData.phone" />
    </div>
    <div style="margin-top: 2rem;">
      <label >Website</label>
      <input type="text" placeholder="Emter Website" v-model="todoData.website" />
    </div>
    <div style="display: flex;" @click="handleCreateNewData">
      <div class="btn-main mt-3" style="border-radius: 40px;">Create new</div>
    </div>
  </main>
</template>

