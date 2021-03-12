<template>
  <div id="app">
    <Header />
    <ListCards />
  </div>
</template>

<script>
import Header from "@/components/Header";
import ListCards from "@/components/ListCards";

export default {
  name: "App",
  components: {
    Header,
    ListCards,
  },
}
</script>


<style>
#app {
  font-family: Avenir, Codec Pro, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0px;
  padding: 0px;
}
body {
  padding: 0px;
  margin: 0px;
}
ul {
  margin: 0px;
  padding: 0px 0px;
}
p {
  padding: 0px;
  margin: 0px;
}
</style>
