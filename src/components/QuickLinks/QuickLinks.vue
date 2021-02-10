<template>
<div>
  <h3>QuickLinks</h3>
  <b-form-input v-model="filterQuery" placeholder="Filter..."></b-form-input>
  <div v-for="group in filteredGroups" :key="group.name">
    <details v-if="group.links.length > 0">
      <summary>{{group.name}} ({{group.links.length}})</summary>
      <ul>
        <li v-for="link in group.links" :key="link.url">
          <a :href="link.url" :title="link.title" target="blank">{{link.title}}</a>
        </li>
      </ul>
    </details>
  </div>
</div>
</template>

<script>

export default {
  name: 'QuickLinks',
  components: {
  },
  props: {
  },
  data() { return {
    filterQuery: null,
    linkGroups: [
      { name:"Communication", links: [
        { title: "Y-Message", url: "https://ymessage.byu.edu"},
        { title: "One Stop", url: "https://onestop.byu.edu"},
      ] },
      
      { name:"Classes and Registration", links: [
        { title: "LearningSuite", url: "https://learningsuite.byu.edu"},
        { title: "Canvas", url: "https://canvas.byu.edu"},
        { title: "MyMap", url: "https://mymap.byu.edu"},
        { title: "Course Catalog", url: "https://catalog.byu.edu"},
      ] },
      
      { name:"Work", links: [
        { title: "Jobs", url: "https://jobs.byu.edu"},
        { title: "Paychecks", url: "https://pay.byu.edu"},
        { title: "W-2", url: "https://w2.byu.edu"},
      ] },
      
      { name:"Empty", links: [] },

    ]
  }},
  computed: {
    filteredGroups() {
      if (!this.filterQuery) return this.linkGroups;

      function contains(query,str) {
        let format = str => str.toLowerCase().replaceAll(/[^\w\d]/g,"");
        str = format(str);
        query = format(query);
        // console.log({str},{query});
        return str.indexOf(query)>-1;
      }

      let query = this.filterQuery;
      return this.linkGroups.map(g => {
        if (contains(query,g.name)) return g;
        else return {
          name: g.name,
          links: g.links.filter(l => contains(query,l.title) || contains(query,l.url))
        }
      })
    }
  }
}
</script>

<style scoped>

</style>
