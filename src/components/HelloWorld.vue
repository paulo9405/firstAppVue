<script setup lang="ts">
import { reactive, ref } from "vue";
 
const name = ref("Paulo");
const form = ref("");

const showDetails = ref<boolean>(false);
const data = reactive({
  name: "Paulo",
  age: 28,
  job: "Developer",
});

console.log(form);

function changeName() {
  name.value = "Paulo Souza";
}

function reset() {
  name.value = "Paulo";
}
</script>

<template>
  <img alt="Vue logo" src="./assets/logo.png" width="100" />
  <h1>Firts App</h1>
  <h3>{{ name }}</h3>
  <form ref="form">
    <button @click="changeName" type="button">Change name</button>
    <button @click="reset" type="button">Back first name</button>
    <button @click="showDetails = !showDetails" type="button">
      Ver detalhes
    </button>
  </form>
  <div class="details">
    <div v-if="showDetails" v-for="item in data" >
      <span>{{ item }}</span>
    </div>
  </div>
</template>

