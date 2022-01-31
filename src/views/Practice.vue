<template>
  <div class="practice">
    <div>
      <h4>Test</h4>
    </div>
    <div>
      <h1>This is an practice page</h1>
    </div>
    <div>
      <label>insert name: </label>
      <input type="text" ref="userInput" />
    </div>
    <div>
      <button @click="setUserInput">Save</button>
    </div>
    <div>
      <PracticeChild :name="name" />
    </div>
  </div>
</template>


<script>
import { defineComponent } from 'vue';
import PracticeChild from './PracticeChild.vue'
import {ref} from 'vue'
export default defineComponent({
  name: 'Practice',
  components: {PracticeChild},
  setup() {
    const name = ref('')
    const userInput = ref(null)

    const setUserInput = () => {
      name.value = userInput.value?.value; // Type Error
      console.log(name.value);
      
    }

return {setUserInput, userInput, name}
  }
})
</script>


<style scoped>
  .practice {
    margin: 3rem auto;
    max-width: 30rem;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    padding: 1rem;
    text-align: center;
  }
</style>

