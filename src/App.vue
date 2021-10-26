<template>
  <div id="app">
    <div class="content-wrapper">
      <directory
        :type="data.type"
        :name="data.name"
        :contents="data.contents"
      />
    </div>
  </div>
</template>

<script>
import data from '../public/static/node_modules.json'
import Directory from "@/components/Directory/Directory";

export default {
  name: 'App',
  components: {
    Directory
  },
  data: () => ({
    data: data,
  }),
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>

<style scoped>
.content-wrapper {
  margin: 0 auto;
  max-width: 1000px;
  min-height: 90vh;
  padding: 30px;
  background-color: #F5F7FA;
  border: 2px solid #216BFF;
}
</style>