<template>
  <head>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Lobster&family=Satisfy&display=swap"
      rel="stylesheet"
    />
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link
      href="https://fonts.googleapis.com/css2?family=Exo+2:wght@300&display=swap"
      rel="stylesheet"
    />
  </head>
  <q-page class="flex flex-center bg-accent">
    <!-- <div class="q-pa-lg row items-start"> -->
    <div class="row q-pl-xl q-ml-xl items-start q-gutter-md">
      <q-card
        v-for="cards in recipeCards"
        :key="cards"
        :class="cards.class"
        align="center"
        id="cards"
      >
        <img :src="cards.img" />

        <q-card-section>
          <div class="text-h6">{{ cards.title }}</div>
          <div class="text-subtitle2">{{ cards.cooktime }}</div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          {{ cards.description }}
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";
import { ref } from "vue";

export default defineComponent({
  name: "PageIndex",
  data() {
    return {
      recipeCards: [
        {
          title: "Fajita Steak with veggies",
          cooktime: "15min",
          description:
            "An easy to make meal that taste great and looks great too!",
          img: [require("../assets/portland_streets2.jpeg")],
          class: "my-card col-4",
        },
        {
          title: "Gourmet Ramen Noodles",
          cooktime: "20mins",
          description: "Taking a classic and making it gourmet",
          img: [require("../assets/portland_streets2.jpeg")],
          class: "my-card col-3 bg-info text-white",
        },
        {
          title: "Beans and Hotdogs",
          cooktime: "20mins",
          description: "Beans + Hotdogs, need I say more?",
          img: [require("../assets/portland_streets2.jpeg")],
          class: "my-card col-4",
        },
        {
          title: "Beef Quesodillas",
          cooktime: "15mins",
          description: "A tasty and easy to make dish for kids and adults!",
          img: [require("../assets/portland_streets2.jpeg")],
          class: "my-card col-4",
        },
        {
          title: "Traditional Zalabia",
          cooktime: "30mins",
          description:
            "A traditional African deseart to make your mouth water and your stomach grumble",
          img: [require("../assets/portland_streets2.jpeg")],
          class: "my-card col-3 bg-info text-white",
        },
        {
          title: "Ethopian Chia",
          cooktime: "45mins",
          description: "Taking a classic Ethopian drink and spazzing it up",
          img: [require("../assets/portland_streets2.jpeg")],
          class: "my-card col-4",
        },
      ],
    };
  },
});
</script>
<style scoped>
#cards {
  font-family: "Exo 2", sans-serif;
  font-weight: 300;
}
</style>
