<template>
  <div class="text-purple-900 m-2 p-2 rounded-md shadow-md shadow-purple-200">
    <div
      v-show="selectedData"
      class="relative font-semibold my-1 tracking-wider"
    >
      price : {{ selectedData?.price }} $
    </div>
    <span v-show="!selectedData?.off == 0" class="absolute top-4 left-16"
      ><svg
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 24 24"
        stroke-width="1.5"
        stroke="#FF0000"
        class="w-6 h-6"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          d="M2.25 6L9 12.75l4.286-4.286a11.948 11.948 0 014.306 6.43l.776 2.898m0 0l3.182-5.511m-3.182 5.51l-5.511-3.181"
        />
      </svg>
    </span>
    <div
      v-show="!selectedData?.off == 0"
      class="font-bold my-1 text-purple-900"
    >
      off price :
      <span class="font-bold my-1 text-purple-900">{{ updoPrice }} $</span>
    </div>
  </div>
</template>
<script>
export default {
  props: ["boxNumber", "newSubs", "selectedData"],

  computed: {
    updoPrice() {
      let curentPrice = this.selectedData?.price;
      this.offPrice = (curentPrice * (100 - this.selectedData?.off)) / 100;
      return this.offPrice;
    },
  },
};
</script>
