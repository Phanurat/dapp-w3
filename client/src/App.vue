<template>
  <div id="app">
    <header>
      <h1>My Dapp</h1>
    </header>
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 50px;
}
</style>
