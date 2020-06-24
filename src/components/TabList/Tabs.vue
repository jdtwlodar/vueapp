<template>
  <div class="tabs-component">
    <ul role="tablist" class="tabs-component-tabs">
      <li
        v-for="(tab, i) in tabs"
        :key="i"
        :class="{ 'is-active': tab.isActive, 'is-disabled': tab.isDisabled }"
        class="tabs-component-tab"
        role="presentation"
        v-show="tab.isVisible"
      >
        <a
          v-html="tab.header"
          @click="selectTab(tab.index, $event)"
          class="tabs-component-tab-a"
          role="tab"
        ></a>
      </li>
    </ul>
    <div class="tabs-component-panels">
      <div
        v-for="(tabc, i) in tabsContent"
        :key="i"
        :class="{ 'is-active': tabc.isActive, 'is-disabled': tabc.isDisabled }"
        class="tabs-component-tab"
        role="presentation"
        v-show="tabc.index == activeTabIndex"
      >
        {{ tabc.content }}
      </div>
      <slot />
    </div>
  </div>
</template>

<script>
/*
import expiringStorage from "../expiringStorage";*/

export default {
  props: {
    cacheLifetime: {
      default: 5,
    },
    options: {
      type: Object,
      required: false,
      default: () => ({
        useUrlFragment: true,
      }),
    },
  },

  data: () => ({
    tabs: [
      {
        header: "ssssssssss",
        isActive: true,
        isVisible: true,
        isDisabled: false,

        index: 0,
        content: "content pierwszego tabas",
      },
      {
        header: "aaaaaaaa",
        isActive: false,
        isVisible: true,
        isDisabled: false,

        index: 1,
        content: "content drugiego tabas",
      },
    ],
    tabsContent: [
      {
        header: "ssssssssss",
        isActive: true,
        isVisible: true,
        isDisabled: false,

        index: 0,
        content: "content pierwszego tabas",
      },
      {
        header: "aaaaaaaa",
        isActive: false,
        isVisible: true,
        isDisabled: false,

        index: 1,
        content: "content drugiego tabas",
      },
    ],
    activeTabHash: "",
    activeTabIndex: 0,
    lastActiveTabHash: "",
    selectedTabHash: "",
  }),
  /*
  created() {
    this.tabs = this.$children;
  },*/

  methods: {
    findTab(index) {
      return this.tabs.find((tab) => tab.index === index);
    },

    selectTab(selectedTabIndex) {
      console.log(this.activeTabIndex);

      this.activeTabIndex = this.getTabIndex(selectedTabIndex);
      
    },

    setTabVisible(index, visible) {
      const tab = this.findTab(index);

      if (!tab) {
        return;
      }

      tab.isVisible = visible;

      if (tab.isActive) {
        // If tab is active, set a different one as active.
        tab.isActive = visible;

        this.tabs.every((tab) => {
          if (tab.isVisible) {
            tab.isActive = true;

            return false;
          }

          return true;
        });
      }
    },

    getTabIndex(index) {
      const tab = this.findTab(index);

      return this.tabs.indexOf(tab);
    },

    getActiveTab() {
      return this.findTab(this.activeTabHash);
    },

    getActiveTabIndex() {
      return this.getTabIndex(this.activeTabIndex);
    },
  },
};
</script>
