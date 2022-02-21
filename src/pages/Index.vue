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

    <div class="q-pt-lg">
      <h4 align="center" class="inherit text-white" id="video-title">
        Recipe of the day
      </h4>
      <iframe
        width="1200"
        height="250"
        src="https://www.youtube.com/embed/ZqEqtmMY1M0?autoplay=1&mute=1"
        frameborder="0"
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
        autoplay
        loop
        allowfullscreen
      ></iframe>
    </div>
    <!-- <Parallax></Parallax> -->
    <div class="row q-pt-xl q-pb-xl q-pl-xl q-ml-xl q-gutter-md" id="container">
      <q-card
        v-for="cards in recipeCards"
        :key="cards"
        :class="cards.class"
        align="center"
        id="cards"
      >
        <q-btn
          align="inherit"
          color="inherit"
          label="recipe"
          class="text-black"
          id="dropdown"
          @click="ingredients"
        />
        <h4 class="text-black">{{ recipeCards.ingredients }}</h4>
        <q-card-section>
          <q-img id="img" :src="cards.img" fit="contain" />

          <div class="text-h6" id="card-title">{{ cards.title }}</div>
          <div class="text-subtitle2" id="card-cooktime">
            {{ cards.cooktime }}
          </div>
        </q-card-section>

        <q-card-section class="q-pt-none">
          {{ cards.description }}
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
import { ref } from "vue";
import { useQuasar } from "quasar";
export default {
  data() {
    return {
      fab1: ref(true),
      recipeCards: [
        {
          title: "Fajita Steak with veggies",
          cooktime: "15min",
          description:
            "An easy to make meal that taste great and looks great too!",
          img: [require("../assets/fajita-4.jpg")],
          class: "my-card col-4",
          id: "card-1",
          ingredients: "steak, fajitas, onions",
        },
        {
          title: "Gourmet Ramen Noodles",
          cooktime: "20mins",
          description: "Taking a classic and making it gourmet",
          img: [require("../assets/ramen.jpg")],
          class: "my-card col-4 bg-info text-white",
          id: "card-2",
          ingredients: "noodles and hot water",
        },
        {
          title: "Beans and Hotdogs",
          cooktime: "20mins",
          description: "Beans + Hotdogs, need I say more?",
          img: [require("../assets/hotdogs.jpg")],
          class: "my-card col-2",
          id: "card-3",
          ingredients: "beans and fresh hot dogs",
        },
        {
          title: "Beef Quesodillas",
          cooktime: "15mins",
          description: "A tasty and easy to make dish for kids and adults!",
          img: [require("../assets/quesodilla.jpg")],
          class: "my-card col-4",
          id: "card-4",
          ingredients: "steak, fajitas, queso sauce and other tings",
        },
        {
          title: "Traditional Zalabia",
          cooktime: "30mins",
          description:
            "A traditional African deseart to make your mouth water and your stomach grumble",
          img: [require("../assets/zalabia.jpg")],
          class: "my-card col-4 bg-info text-white",
          id: "card-5",
          ingredients: "fried food lol, fajitas, onions",
        },
        {
          title: "Ethopian Chia",
          cooktime: "45mins",
          description: "Taking a classic Ethopian drink and spazzing it up",
          img: [require("../assets/tea.jpg")],
          class: "my-card col-2",
          id: "card-6",
          ingredients: "steak, fajitas, onions",
        },
      ],
    };
  },
  setup() {
    const $q = useQuasar();
    function ingredients() {
      $q.dialog({
        title: "the recipe for this dish is",
        message: "working on this",
        persistent: true,
        cancel: true,
        dark: true,
      });
    }
    return {
      ingredients,
    };
  },
  name: "PageIndex",
  components: {},
};
</script>
<style scoped>
#cards {
  font-family: "Exo 2", sans-serif;
  font-weight: 300;
  position: relative;
  display: inline-block;
  /* inset-inline: left; */
  /* justify-content: inherit; */
  /* white-space: pre-wrap; */
  /* inset-inline-start: 200; */
}
#container {
  padding-left: 10%;
  font-size: 20px;
}
#img {
  object-fit: cover;
}
#video-title {
  font-family: "Exo 2", sans-serif;
}
#dropdown {
  display: none;
  position: absolute;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  padding: 12px 16px;
  z-index: 1;
}

#cards:hover #dropdown {
  display: block;
}
@media screen and (max-width: 300px) {
  #cards {
    font-size: small;
    max-width: 300px;
    flex-wrap: wrap;
    object-fit: contain;
    height: 200px;
    -ms-flex-direction: column-reverse;
    flex-direction: column-reverse;
  }
  #img {
    object-fit: fill;
  }
  #card-cooktime {
    font-size: small;
  }
  #card-title {
    font-size: small;
  }
}
</style>
