<template>
  <div
    class="shadow-md rounded-md p-10 pt-2 mt-10 h-96 flex flex-col max-w-fit mx-auto justify-center"
  >
    <HeaderBadge :acitveData="acitveData" />

    <div class="flex">
      <SubBtn
        :is_selected="subDuration.is_selected"
        @activeDuration="(data) => (acitveData = data)"
        :index="i + 1"
        :newSubs="subDuration"
        v-for="subDuration in subs"
      />
    </div>

    <OffHandler :selectedData="acitveData" />
  </div>
</template>
<script>
import SubBtn from "./Sub-btn.vue";
import HeaderBadge from "./HeaderBadge.vue";
import OffHandler from "./components/Off-handler.vue";

export default {
  props: ["boxNumber", "subs"],
  components: {
    SubBtn,
    HeaderBadge,
    OffHandler,
  },
  data() {
    return {
      acitveData: null,
      i: 1,
      newSubs: null,
    };
  },
  created() {
    this.newSubs = this.subs.reduce((subs, objSubs) => {
      subs[objSubs.id] = objSubs;

      return subs;
    }, {});
  },
  watch: {
    acitveData(val) {
      console.log("from watcher: ", val);
    },
  },
  computed: {
    subHandler() {
      let data = this.newSubs;

      return data;
    },
    changeID() {
      return this.subHandler.id;
    },
  },
};
</script>
