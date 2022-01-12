<template>
  <ul>
    <li v-for="resource in resources" :key="resource.id">
      <ResourceCard
        :id="resource.id"
        :title="resource.title"
        :description="resource.description"
        :link="resource.link"
      />
    </li>
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