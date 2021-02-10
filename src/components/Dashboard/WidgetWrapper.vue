<template>
  <b-card header-tag="header" class="shadow-sm bg-white">
    <template #header>
      {{data.title}}
      <BIconPencilFill />
      <BIconTrashFill />
    </template>
    <div class="widget-content-wrapper">
      <slot></slot>
    </div>
  </b-card>
</template>

<script>
import { BIconPencilFill, BIconTrashFill } from 'bootstrap-vue'

export default {
  name: 'WidgetHeader',
  props: {
    data:Object,
  },
  components: {
    BIconPencilFill,
    BIconTrashFill,
  },
  data() { return {
  }}
}
</script>

<style scoped>
</style>
