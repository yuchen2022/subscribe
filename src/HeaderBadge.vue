<template>
  <div class="flex justify-between mb-3">
    <div
      v-show="acitveData?.off"
      class="bg-purple-200 p-2 rounded-md w-1/3 text-center text-lg shadow-md shadow-purple-400 font-extrabold text-purple-900"
    >
      off : {{ offPrice }} %
    </div>
    <div
      v-show="acitveData?.is_selected"
      class="bg-purple-200 p-2 rounded-md w-1/3 tracking-wider text-center text-lg shadow-md shadow-purple-400 font-extrabold text-purple-900"
    >
      special offer!
    </div>
  </div>
  <div class="bg-purple-950 mb-4 text-white p-3 rounded-md">
    subscription {{ i }}
  </div>
</template>
<script>
export default {
  props: ["boxNumber", "newSubs", "acitveData"],
  data() {
    return {
      i: 3,
    };
  },
  computed: {
    offPrice() {
      console.log("header :", this.acitveData);
      return this.acitveData?.off;
    },
  },
};
</script>
