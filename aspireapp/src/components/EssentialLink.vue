<template>
  <q-item clickable :to="link">
    <q-item-section v-if="icon" avatar>
      <q-icon  :class="activeClass==title?'q-pl-md text-green':'q-pl-md text-white'" :name="icon" />
      <q-item-label v-if="caption" :class="activeClass==title?'q-pa-sm text-green':'q-pa-sm text-white'">{{ title }}</q-item-label>
    </q-item-section>

    <q-item-section>
      <q-item-label :class="activeClass==title?'q-pa-sm text-green':'q-pa-sm text-white'" v-if="!caption">{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script>
import { defineComponent,ref } from "vue";

export default defineComponent({
  name: "EssentialLink",
  props: {
    title: {
      type: String,
      required: true,
    },

    caption: {
      type: Boolean,
      default: false,
    },

    link: {
      type: String,
      default: "",
    },

    icon: {
      type: String,
      default: "",
    },
    activeClass: {
      type:String,
      defualt: ""
    }
  },
  setup () {
    return {
           
    }
  } 
});
</script>
