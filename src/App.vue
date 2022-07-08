<template>
  <div id="app">
    <!-- HEADER -->
    <HeaderComponent/>
    <!-- MAIN -->
    <main>
      <!-- first section -->
      <FirstSectionComponent/>
    </main>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import FirstSectionComponent from './components/FirstSectionComponent.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    FirstSectionComponent,
  }
}
</script>

<style lang="scss">
// *IMPORTS
@import "./style/common.scss";

</style>
