<template>
  <div class="hello">
   <h3>Site Overview for site "{{site.title}}" with ID "{{site.id}}"</h3>
   
   <ul>
      <li>
        Number of rooms: {{site.rooms}}
      </li>
      <li>
         Telephone number: {{site.telephone}} 
      </li>
   </ul>
    
  </div>
</template>

<script>

export default {
  name: "SiteOverview",
  components: {
  },
  props: {
    site: Object,
  },
  mounted() {
    console.log("Site passed is "+this.site);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
