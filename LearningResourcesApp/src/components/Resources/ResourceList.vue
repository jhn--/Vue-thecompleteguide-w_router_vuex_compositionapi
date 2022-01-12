<template>
  <ul>
    <resource-card
      v-for="resource in resources"
      :key="resource.id"
      :id="resource.id"
      :title="resource.title"
      :description="resource.description"
      :link="resource.link"
      :logo="resource.logo"
    >
    </resource-card>
  </ul>
</template>

<script>
import ResourceCard from './ResourceCard.vue';

export default {
  components: {
    ResourceCard,
  },
  props: {
    resources: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style>
</style>