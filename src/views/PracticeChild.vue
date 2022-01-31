<template>
  <div>
    <div class="practice-child">Hello World</div>
    <div>{{firstName}}</div>
  </div>
</template>

<script lang="ts">
import { defineComponent, computed } from 'vue';

export default defineComponent({
  props: ['name'],
  setup(props) {
    
    const firstName = computed(() => {
      return props.name
    });
    return {
      firstName
    }
  },
})
</script>


<style scoped>
  .practice-child{
    padding-top: 100px;
  }
</style>