<template>
  <button
    :class="{ 'bg-purple-700 text-white': is_selected }"
    @click="() => $emit('activeDuration', newSubs)"
    class="bg-fuchsia-200 rounded-lg whitespace-nowrap text-purple-800 shadow-md shadow-purple-500 px-2 font-semibold p-2 m-3 focus:bg-purple-600 focus:text-purple-100"
  >
    duration :
    {{ durTime }} days
  </button>
</template>
<script>
export default {
  emits: ["activeDuration"],

  props: {
    index: {
      default: 1,
    },
    newSubs: {
      type: Object,
    },
    is_selected: {
      type: Boolean,
    },
  },

  created() {
    if (this.is_selected) {
      this.$emit("activeDuration", this.newSubs);
    }
  },
  computed: {
    durTime() {
      let durTime = this.newSubs.duration;
      return durTime / 3600 / 24;
    },
  },
};
</script>
