<template>
  <div class="card">
    <div class="card-header">
      <ul class="tab-heads">
        <li
          class="tab-head"
          v-for="tab in tabs"
          :key="tab"
          v-bind:class="{
            'tab-head--active': activeTab === tab
          }"
          v-on:click="switchTab(tab);"
        >
          <slot :name="tabHeadSlotName(tab)">{{ tab }}</slot>
        </li>
      </ul>
    </div>
    <main class="card-body">
      <div class="tab-panel">
        <slot :name="tabPanelSlotName"></slot>
      </div>
    </main>
  </div>
</template>

<script>
export default {
  name: "app-tab",
  props: {
    initialTab: String,
    tabs: Array
  },
  data() {
    return {
      activeTab: this.initialTab
    };
  },
  computed: {
    tabPanelSlotName() {
      return `tab-panel-${this.activeTab}`;
    }
  },
  methods: {
    tabHeadSlotName(tabName) {
      return `tab-head-${tabName}`;
    },

    switchTab(tabName) {
      this.activeTab = tabName;
    }
  }
};
</script>

<style scoped>
.card {
  background-color: #fff;
  border-radius: 6px;
  box-shadow: 2px 0px 30px 0 rgba(0, 0, 0, 0.14);
}

.card-header {
  background-color: var(--green);
  display: flex;
  align-items: flex-start;
  justify-content: space-between;
  color: var(--font);
  padding: 15px 8px 0;
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
}

.tab-heads {
  display: flex;
  margin: 0;
  padding: 0;
  list-style: none;
  margin-left: 6px;
  margin-top: -4px;
}

.tab-head {
  padding: 0.5rem;
  border-top-left-radius: 4px;
  border-top-right-radius: 4px;
  position: relative;
  cursor: pointer;
}

.tab-head--active {
  background-color: #fff;
  color: var(--font);
  transition: 0.4s;
}

.card-body {
  padding: 20px 16px;
}

@media screen and (min-width: 45rem) {
  .tab-head {
    padding: 1.5rem;
  }
}
</style>