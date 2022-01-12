<template>
  <nav
    class="navbar has-background-primary is-size-5 block"
    role="navigation"
    aria-label="main navigation"
  >
    <div id="navbar" class="navbar-menu">
      <div class="navbar-start">
        <a
          class="navbar-item has-text-white"
          @click="setSelectedTab('resource-list')"
        >
          Resource List
        </a>
        <a
          class="navbar-item has-text-white"
          @click="setSelectedTab('add-resource')"
        >
          Add Resource
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  methods: {
    setSelectedTab(cmp) {
      this.$emit('select-tab', cmp);
    },
  },
};
</script>

<style>
</style>