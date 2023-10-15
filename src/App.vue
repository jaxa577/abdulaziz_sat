<script>
import { RouterLink, RouterView } from "vue-router";
import mainHeader from "./components/MainHeader.vue";
import mainFooter from "./components/MainFooter.vue";

export default {
  components: {
    mainHeader,
    mainFooter,
  },

  mounted() {
    // this.postForm();
  },

  methods: {
    postForm() {
      fetch(`https://abdulaziz-bot.onrender.com/send`, {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify({
          todos: "Khabibjonov Javokhir",
          fio: "19",
          startDate: "Intermediate",
          endDate: "Knows 9th grade algebra",
          hourly: "+998919745700",
          userName: "@jaxa_577",
          addMessage: `\n Hello Mr. Abdulaziz, one of the greatest coach I've ever met`,
        }),
      });
    },
  },
};
</script>

<template>
  <mainHeader />
  <main>
    <RouterView />
  </main>
  <mainFooter />
</template>

<style scoped></style>
