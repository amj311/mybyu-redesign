<template>
  <div>
      <div class="icon-wrapper" v-b-modal.modal-1>
        <BIconPlusCircleFill font-scale="8" />
      </div>

      <b-modal id="modal-1" centered title="BootstrapVue">
      <p class="my-4">Hello from modal!</p>
    </b-modal>
  </div>
</template>

<script>
import { BIconPlusCircleFill } from 'bootstrap-vue'

export default {
  name: 'AddWidget',
  components: {
    BIconPlusCircleFill
  },
  props: {
    // widgetId: String
  },
  data() { return {
    title: "Add A Widget",
  }}
}
</script>

<style scoped>
  .icon-wrapper {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: grid;
    place-items: center;
    cursor: pointer;
  }
  .icon-wrapper:hover {
    color: var(--royal)
  }
</style>
