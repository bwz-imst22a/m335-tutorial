<template>
<div v-for="row in 3" class="row">
  <field v-for="col in 3" :value="fields[row - 1][col - 1]" @fieldClick="handleClick(row - 1, col - 1)" />
</div>
</template>
  
<script setup lang="ts">
import { ref } from 'vue';
import Field from './Field.vue';

const fields = ref( [
  [ '', '', '' ],
  [ '', '', '' ],
  [ '', '', '' ]
] );
const handleClick = (row: number, col: number) => {
    fields.value[row][col] = 'X';
}
</script>
  
<style scoped>
.row {
  display: flex;
  flex-direction: row;
}
</style>