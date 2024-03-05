<script setup>
import Navbar from './components/Navbar.vue';
import ReactiveComponent from './components/ReactiveComponent.vue';
import ComputedProperties from './components/ComputedProperties.vue';
import ComponentProps from './components/ComponentProps.vue';
import EmitComponent from './components/EmitComponent.vue';
import EmptySlot from './components/slot/EmptySlot.vue';
import FallbackSlot from './components/slot/FallbackSlot.vue';
import NamedSlot from './components/slot/NamedSlot.vue';
// import CreatePage from './components/CreatePage.vue';
import { ref } from 'vue';
import { provide } from 'vue';

const buttonColor = ref('red')

const formHandler = (username, email, password) => {
  console.log("username", email, password);
}

provide("games", {
  name: "gta",
  genre: ["adventure", "action"]
})

provide("books", ["SHerlock Holmes", "Dune"]);

</script>

<template>
  <Navbar />
  <!-- <ReactiveComponent /> -->
  <ComputedProperties />

  <input type="text" v-model="buttonColor">
  <ComponentProps employee="Bob" age=25 fullName="johnDoe" :buttonColor="buttonColor" name="Alice" />

  <EmitComponent @userInfo="formHandler" />

  <EmptySlot>
    <h1>This is an empty slot</h1>
  </EmptySlot>

  <FallbackSlot>
    <!-- if nothing is passed here the default content will be shown -->
  </FallbackSlot>

  <NamedSlot>
    <template v-slot:one>
      This content will go to slot one.
    </template>

    <template #two>
      This content will go to slot two
    </template>
  </NamedSlot>


  <!-- <ComponentProps  /> -->

  <!-- <CreatePage /> -->
</template>

<style scoped></style>
