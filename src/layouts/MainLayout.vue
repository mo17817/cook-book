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
  <q-layout view="lHh Lpr lFf">
    <q-header elevated id="title">
      <q-toolbar>
        <q-btn flat @click="drawerLeft = !drawerLeft" round dense icon="menu" />
        <q-toolbar-title align="center"> Recepies Galore </q-toolbar-title>
      </q-toolbar>
    </q-header>
    <q-drawer
      v-model="drawerLeft"
      :width="200"
      :breakpoint="700"
      bordered
      id="drawer"
    >
      <q-scroll-area class="fit" id="drawer">
        <q-list id="drawer">
          <div class="q-pa-sm bg-accent text-white">
            <template v-for="links in linksList" :key="links">
              <q-item
                clickable
                :active="links.link"
                :href="links.link"
                v-ripple
              >
                <q-item-section avatar>
                  <q-icon :name="links.icon" />
                  <h6 style="font-family: 'Exo 2', sans-serif" font-size="15px">
                    {{ links.title }}
                  </h6>
                </q-item-section>
              </q-item>
            </template>
          </div>
        </q-list>
      </q-scroll-area>
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
// const linksList = [
//   {
//     title: "Find more recipes online",
//     icon: "food",
//     link: "https://www.foodnetwork.com/",
//     seperator: true,
//   },
//   {
//     title: "Share a recipe!",
//     icon: "code",
//     link: "https://www.instagram.com/mo_ahmed00",
//   },
// ];

import { defineComponent, ref } from "vue";
export default defineComponent({
  name: "MainLayout",
  components: {},
  setup() {
    return {
      drawerLeft: ref(false),
      linksList: [
        {
          title: "Find more recipes online",
          icon: "fastfood",
          link: "https://foodnetwork.com",
          seperator: true,
        },
        {
          title: "Share a recipe!",
          icon: "share",
          link: "https://www.instagram.com/mo_ahmed00",
        },
      ],
    };
  },
});
</script>
<style scoped>
#title {
  background-image: linear-gradient(to right, #decba4, #3e5151);
  font-family: "Exo 2", sans-serif;
  font-size: 70px;
}
#drawer {
  background-image: linear-gradient(to right, #decba4, #3e5151);
}
</style>
