<template>
  <div>
    <Tabs />
  </div>
</template>

<script>
import Tabs from "./TabList/Tabs.vue";
export default {
  name: "QA",

  data() {
    return {
      tabIndex: 0,
    };
  },
  components: {
    Tabs,
  },

  methods: {
    linkClass(idx) {
      if (this.tabIndex === idx) {
        return ["bg-primary", "text-light"];
      } else {
        return ["bg-light", "text-info"];
      }
    },
  },
};
</script>
