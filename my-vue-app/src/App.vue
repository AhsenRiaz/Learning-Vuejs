<script>
import Navbar from './components/Navbar.vue';
import ReactiveComponent from './components/ReactiveComponent.vue';
import ComputedProperties from './components/ComputedProperties.vue';
// import CreatePage from './components/CreatePage.vue';

export default {
  components: {
    Navbar,
    // ReactiveComponent,
    ComputedProperties

    // CreatePage
  },
}

</script>

<template>
  <Navbar />
  <!-- <ReactiveComponent /> -->
  <ComputedProperties />
  <!-- <CreatePage /> -->
</template>

<style scoped></style>
