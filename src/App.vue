<template>
  <div>
    <SubscribeBox v-for="sub in subs" :boxNumber="i" :subs="sub" />
    <div>{{ boxNumber }}</div>
  </div>
</template>
<script>
import SubscribeBox from "./SubscribeBox.vue";

export default {
  data() {
    return {
      i: 1,
      subs: {
        subscription_1: [
          {
            id: 1,
            price: 100,
            duration: 86400,
            off: 0,
            is_selected: false,
          },
          {
            id: 2,
            price: 200,
            duration: 2592000,
            off: 0,
            is_selected: false,
          },
          {
            id: 3,
            price: 300,
            duration: 31536000,
            off: 10,
            is_selected: true,
          },
        ],
        subscription_2: [
          {
            id: 4,
            price: 400,
            duration: 86400,
            off: 0,
            is_selected: false,
          },
          {
            id: 5,
            price: 500,
            duration: 2592000,
            off: 0,
            is_selected: false,
          },
          {
            id: 6,
            price: 600,
            duration: 31536000,
            off: 10,
            is_selected: false,
          },
        ],
        subscription_3: [
          {
            id: 7,
            price: 700,
            duration: 86400,
            off: 40,
            is_selected: false,
          },
          {
            id: 8,
            price: 800,
            duration: 2592000,
            off: 0,
            is_selected: false,
          },
          {
            id: 9,
            price: 900,
            duration: 31536000,
            off: 10,
            is_selected: false,
          },
        ],
      },
    };
  },
  computed: {
    boxNumber() {
      console.log(this.subs.subscription_2[this.i]);
    },
  },
  components: { SubscribeBox },
};
</script>
