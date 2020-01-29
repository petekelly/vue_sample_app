<template>
  <div class="home">
    <img alt="iBrowse logo" src="../assets/logo-ibrowse.gif" />
    <SiteList msg="Welcome to the iBrowse overview page" :siteList="siteList" :site="selectedSiteObject" />
  </div>
</template>

<script>
// @ is an alias to /src
import SiteList from "@/components/SiteList.vue";

export default {
  name: "home",
  components: {
    SiteList
  },
  props: {
    site: String
  },
  // Because this component is reused when the URL changed, its state will always persist from the first time it was loaded.
  // By 'watching' the route object for changes we can detect when the state may need refreshing
  watch: { 
    $route: function() {
      this.logSitePassed();
      this.loadSiteList();
      this.setSiteObject();
    }
  },
  mounted() {
    this.logSitePassed();
    this.loadSiteList();
    this.setSiteObject();
  },
  methods: {
    logSitePassed() {
      console.log("Site passed is "+this.site);
    },
    setSiteObject() {
      this.selectedSiteObject = this.siteList.find(site => site.id == this.site);
    },
    loadSiteList() {
      this.siteList=[
        { id: 'FRA1234', title: 'Hotel 1', rooms: "23", telephone: "+33 111222888" },
        { id: 'FRA5678', title: 'Hotel 2', rooms: "100", telephone: "+33 432435335" },
        { id: 'FRA7777', title: 'Hotel 3', rooms: "145", telephone: "+33 355324335" },
      ]
    }
  },
  data: function () {
    return {
      siteList: [],
      selectedSiteObject: {}
    }
  }
};
</script>
