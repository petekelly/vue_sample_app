<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>List of sites:</h3>
    <table v-if="siteList.length > 0">
      <tr>
        <td>ID</td>
        <td>Name</td>
      </tr>

      <SiteRow
        v-for="site in siteList"
        v-bind:key="site.id"
        v-bind:site="site"
      ></SiteRow>

      <SiteOverview v-if="site" :site="site"></SiteOverview>

    </table> 
  </div>
</template>

<script>
import SiteRow from "@/components/SiteRow.vue";
import SiteOverview from "@/components/SiteOverview.vue";

export default {
  name: "SiteList",
  components: {
    SiteRow,
    SiteOverview
  },
  props: {
    msg: String,
    siteList: Array,
    site: Object,
  },
  mounted() {
    console.log("Site List passed is "+this.siteList);
    console.log("Site passed is "+this.site);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
table {
  list-style-type: none;
  padding: 0;
}
table {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
