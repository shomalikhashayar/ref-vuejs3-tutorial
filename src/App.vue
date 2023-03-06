<template>
  <div class="container">
    <h2>What is ref () in Vue 3?</h2>
  </div>
  <div class="show-answer">
    <button @click="showMeTheAnswer">Show Me the Answer!</button>
  </div>
  <div class="answer-paragraph" v-if="showParagraph && showVueLogo">
    {{ paragraph }}
    <a href="https://vuejs.org/guide/essentials/template-refs.html"
      ><img v-bind:src="vueLogo"
    /></a>
  </div>
</template>

<script setup>
import { ref } from "vue";

const showParagraph = ref(false);
const showVueLogo = ref(false);

const paragraph = ref(
  "Ref() and Reactive() are the new ways of creating reactive property introduced in Composition API Vue 3. They are wrapper objects that can be initialized with inner values and assigned to variables. In Vue 3, we need to import the desired package first before using it in the component. "
);

const vueLogo = ref(require("../src/assets/logo.png"));

const showMeTheAnswer = () => {
  showParagraph.value = ref(true);
  showVueLogo.value = ref(true);
};
</script>

<style>
* {
  font-family: sans-serif;
}
body {
  margin-top: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.show-answer {
  display: flex;
  justify-content: center;
  align-items: center;
}
.show-answer button {
  background-color: rgb(197, 255, 240);
  font-size: 22px;
  padding: 20px 40px;
  cursor: pointer;
  border-radius: 9px;
  font-weight: 400;
}

.show-answer button:hover {
  background-color: rgb(0, 255, 170);
}

.container h2 {
  text-align: center;
}
.container p {
  width: 700px;
  line-height: 25px;
  text-align: center;
}

.answer-paragraph {
  width: 700px;
  line-height: 25px;
  text-align: center;
  margin-top: 50px;
}

.answer-paragraph img {
  margin-top: 50px;
}

/* Mobile Screens */

@media screen and (max-width: 400px) {
  .container h2 {
    font-size: 18px;
  }

  .show-answer button {
    padding: 10px 25px;
    font-size: 16px;
  }

  .answer-paragraph {
    max-width: 300px;
  }
}
</style>
