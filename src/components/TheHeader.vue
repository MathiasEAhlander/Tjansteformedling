<template>
  <header>
    <div class="banner">
      <h1>{{ title }}</h1>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {};
  },
  props: ["title"],
};
</script>

<style>
h1 {
  margin: 10px;
}
body {
  padding: 0%;
  margin: 0%;
}
.banner {
  border-bottom: solid black 5px;
  width: 100%;
  background-color: blue;
  height: 150px;
  margin-bottom: 200px;
  position: fixed;
  top: 0px;
}
</style>
