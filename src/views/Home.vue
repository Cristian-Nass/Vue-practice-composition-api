<template>
  <section class="container">
    <h2>{{userName}}</h2>
    <h2>{{changeName}}</h2>
    <h2>{{user.name}} - {{user.age}}</h2>
    <button @click="setNewData">Console Log</button>
    <input v-model="changeName"/>
  </section>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { ref, reactive, watch } from 'vue'; // Use reactive for Object and ref for others Data

export default defineComponent({
  name: 'Home',
  components: {
  },
  setup() {
    const userName = ref('Cristian');
    const changeName = ref('');
    const user = reactive({
      name: 'Ronak',
      age: 37
    });

    // setTimeout(() => {
    //   userName.value = 'Nasirabdi'
    // }, 1000);

    setTimeout(() => {
      user.age = 38
    }, 500);

    console.log(userName);
    console.log(user.age);
    console.log(user);
    
    const setNewData = () => {
      console.log('Test');
    }

    // const uName = computed(() => {
    //   return changeName.value
    // });

    watch(changeName, (newValue, oldValue) => {
      console.log('OLD :' + oldValue);
      console.log('NEW :' + newValue);
      
    });

    return {userName, user: user, setNewData, changeName}
  }
});
</script>
