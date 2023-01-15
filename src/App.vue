<template>
  <h1>Demo1</h1>
  <div class="color-container">
    <div v-for="(color, index) of red" :key="color" class="color-item" :style="{
      backgroundColor: color,
      color: index >= 5 ? 'white' : 'rgba(0,0,0,0.85)',
    }">
      <span class="color-text">red-{{ index }}</span>
      <span class="color-value">{{ color }}</span>
    </div>
  </div>
</template>
  
<script setup lang='ts'>
import { red } from '@ant-design/colors'
</script>
  
<style scoped>
.color-container {
  --item-add-width: 12px;
  --border-radius: 5px;
  --transition-duration: .3s;
  --left-width: 5px;
  width: 300px;
  border-radius: var(--border-radius);
  overflow: hidden;
  cursor: pointer;
}

.color-container:hover .color-value {
  left: 0;
  opacity: .7;
}

.color-item {
  display: flex;
  justify-content: space-between;
  padding: 10px 15px;
  overflow: hidden;
  margin-right: var(--item-add-width);
  transition: all var(--transition-duration);
}

.color-item:hover {
  margin-right: calc(- var(--item-add-width));
  border-radius: 0 var(--border-radius) var(--border-radius) 0;
}

.color-value {
  opacity: 0;
  transition: all var(--transition-duration);
  position: relative;
  left: var(--left-width);
}
</style>
