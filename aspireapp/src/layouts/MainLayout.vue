<template>
  <q-layout view="lHh Lpr lFf">
  
    <q-drawer v-model="leftDrawerOpen" show-if-above bordered v-if="$q.platform.is.desktop">
  
      <div class="q-pa-lg">
        <img alt="digital banking singapore" src="https://global-uploads.webflow.com/5ed5b60be1889f546024ada0/5ed8a32c8e1f40c8d24bc32b_Aspire%20Logo%402x.png" style="width: 128px" />
        <q-item-label caption class="q-pa-sm">
          Trusted way of banking 3000+ SMEs and startups in Singapore
        </q-item-label>
      </div>
  
  
      <q-list>
        <EssentialLink v-for="link in essentialLinks" :activeClass="activeClass" :key="link.title" v-bind="link" @click="selectClass(link.title)" />
      </q-list>
    </q-drawer>
  
    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer elevated class="bg-grey-8 text-white">
      <div class="row">
  
        <EssentialLink v-for="link in essentialLinks" :key="link.title" :activeClass="activeClass" v-bind="link" caption="true" @click="selectClass(link.title)" />
  
      </div>
    </q-footer>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink.vue";

const linksList = [
  {
    title: "Home",
    icon: "mdi-chevron-up-circle-outline",
    link: "/"
  },
  {
    title: "Cards",
    icon: "credit_card",
    link: "card"
  },
  {
    title: "Payments",
    icon: "swap_horizontal_circle",
    link: "/"
  },
  {
    title: "Credit",
    icon: "arrow_circle_up",
    link: "/"
  },
  {
    title: "Settings",
    icon: "person_outline",
    link: "/"
  }
];

import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "MainLayout",

  components: {
    EssentialLink
  },

  setup() {
    const leftDrawerOpen = ref(false);

    return {
      essentialLinks: linksList,
      activeClass: ref(""),
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value;
      }
    };
  },
  methods: {
    selectClass(title) {
      this.activeClass = title;
    }
  }
});
</script>

<style>
.q-drawer {
  background-color: darkslategray;
}
</style>

