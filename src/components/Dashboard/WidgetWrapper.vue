<template>
  <b-card header-tag="header" class="shadow-sm bg-white">
    <template #header>
      <div class="widget-header">
        <span class="widget-title">{{data.title}}</span>
        <BIconPencilFill />
        <BIconTrashFill />
      </div>
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
.widget-header {
  display: flex;
}
.widget-title {
  flex-grow: 1;
}
</style>
