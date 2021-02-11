<template>
  <div>
    <h5>Dashboard</h5>
    <div class="widgets-container">
      <div class="widget-wrapper" v-for="(widget,i) in userWidgets" :key="i">
        <WidgetWrapper :data="widget">
          <component :is="widget.name" />
        </WidgetWrapper>
      </div>
      <div class="widget-wrapper">
        <WidgetWrapper :data="addWidget">
          <component :is="addWidget.name" />
        </WidgetWrapper>
      </div>
    </div>
  </div>
</template>

<script>
import WidgetWrapper from './WidgetWrapper.vue'
import AddWidget from './widgets/AddWidget.vue'

export default {
  name: 'Dashboard',
  components: {
    WidgetWrapper,
    AddWidget
  },
  props: {
  },
  data() { return {
    addWidget: {name:"AddWidget",title:"Add a widget!"},
  }},
  computed: {
    userWidgets() {
      return [
        // {name:"AddWidget",title:"Add a widget!"},
      ]
    }
  }
}
</script>

<style scoped>
.widgets-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}

.widget-wrapper {
  margin-top: 1em;
  display: flex;
  width: 7em;
  height: 20em;
  flex-basis: 32%;
}
.widget-wrapper > .card {
  width: 100%;
}

@media screen and (max-width: 500px) {
  .widget-wrapper {
    flex-basis: 100%;
  }
}
</style>
