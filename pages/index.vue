<template>
<div>
  <NavigationBar />
  <LogoPart />
  <TopNewsCard />
 
</div>
</template>

<script>
import LogoPart from '../components/LogoPart.vue'
import NavigationBar from '../components/NavigationBar.vue'
import NewsCard from '../components/NewsCard.vue'
import TopNewsCard from '../components/TopNewsCard.vue'
export default {
  components: { NavigationBar, NewsCard, TopNewsCard, LogoPart },}
</script>

