<template>
	<h1>Demo1</h1>
	<div class="color-container">
		<div
			v-for="(color, index) of green"
			:key="color"
			class="color-item"
			:style="{
				backgroundColor: color,
				color: index >= 5 ? 'white' : 'rgba(0,0,0,0.85)',
			}"
		>
			<span class="color-text">red-{{ index }}</span>
			<span class="color-value">{{ color }}</span>
		</div>
	</div>
</template>

<script setup lang="ts">
import { green } from '@ant-design/colors'
</script>

<style scoped lang="scss">
.color-container {
	--item-add-width: 12px;
	--border-radius: 10px;
	--transition-duration: 0.3s;
	--left-width: 5px;
	width: 300px;
	overflow: hidden;
	cursor: pointer;
}

.color-container:hover .color-value {
	left: 0;
	opacity: 0.7;
}

.color-item {
	display: flex;
	justify-content: space-between;
	padding: 10px 15px;
	overflow: hidden;
	margin-right: var(--item-add-width);
	transition: all var(--transition-duration);

	&:first-child {
		border-radius: var(--border-radius) var(--border-radius) 0 0;
	}
	&:last-child {
		border-radius: 0 0 var(--border-radius) var(--border-radius);
	}
	&:hover {
		margin-right: calc(0 - var(--item-add-width));
    border-radius: 0 var(--border-radius) var(--border-radius) 0;
	}
}

.color-value {
	opacity: 0;
	transition: all var(--transition-duration);
	position: relative;
	left: var(--left-width);
}
</style>
