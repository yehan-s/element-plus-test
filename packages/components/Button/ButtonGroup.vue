<template>
  <div class="ye-button-group">
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
import { BUTTON_GROUP_CTX_KEY } from './contants'
import type { ButtonGroupProps } from './types'
import { provide, reactive, toRef } from 'vue'

defineOptions({
  name: 'YeButtonGroup',
})
const props = defineProps<ButtonGroupProps>()

provide(
  BUTTON_GROUP_CTX_KEY,
  reactive({
    size: toRef(props, 'size'),
    type: toRef(props, 'type'),
    disabled: toRef(props, 'disabled'),
  })
)
</script>

<style scoped>
@import './style.css';
</style>
