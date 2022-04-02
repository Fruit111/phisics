<template>
  <q-layout view="hHh Lpr lFf">
    <q-header>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />
      </q-toolbar>

      <div class="q-pt-xl q-pa-md">
        <div class="text-h3">Физика</div>
        <div class="text-subtitle">{{ Date() }}</div>
      </div>
      <img
        src="../assets/header_light.jpg"
        style="
          position: absolute;
          top: 0;
          z-index: -1;
          height: 100%;
          width: 100%;
          opacity: 0.7;
        "
      />
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header> Полезные ссылки </q-item-label>

        <EssentialLink
          v-for="link in essentialLinks"
          :key="link.title"
          v-bind="link"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink.vue";

const linksList = [
  {
    title: "Новости физики",
    caption: "Новости",
    icon: "school",
    link: "https://new-science.ru/category/fizika/",
  },
  {
    title: "HABR",
    caption: "Физика Хабр",
    icon: "code",
    link: "https://habr.com/ru/hub/physics/",
  },
];

import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",
  data() {
    return {
      today: "",
    };
  },

  components: {
    EssentialLink,
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      },
    };
  },
});
</script>
