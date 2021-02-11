<template>
  <b-card header-tag="header" class="shadow-sm bg-white widget-container">
    <template #header>
      <div class="widget-header" draggable>
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
  cursor: grab;
}
.widget-header:active {
  display: flex;
  cursor: grabbing;
}
.widget-title {
  flex-grow: 1;
}


.widget-container .card-body {
  display:flex;
}

.widget-content-wrapper {
  font-size: .9em;
  flex: 1 1 auto;
  overflow: auto;
  position: relative;
}
</style>
