<template>
  <div>
    <h3>Dashboard</h3>
    <div class="widgets-container">
      <div class="widget-wrapper" v-for="(widget,i) in userWidgets" :key="i">
        <WidgetWrapper :data="widget">
          <component :is="widget.name" />
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
  computed: {
    userWidgets() {
      return [
        {name:"AddWidget",title:"Add a widget!"},
        {name:"AddWidget",title:"Add a widget!"},
        {name:"AddWidget",title:"Add a widget!"},
      ]
    }
  }
}
</script>

<style scoped>
.widgets-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}

.widget-wrapper {
  margin: .5em;
  display: flex;
  width: 7em;
  height: 20em;
  flex-basis: 45%;
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
