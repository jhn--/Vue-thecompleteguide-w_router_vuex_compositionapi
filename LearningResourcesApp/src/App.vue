<template>
  <ResourceList :resources="storedResources" />
</template>

<script>
import { uuid } from 'vue-uuid';

import ResourceList from './components/Resources/ResourceList.vue';

export default {
  components: {
    ResourceList,
  },
  data() {
    return {
      storedResources: [
        {
          id: uuid.v4(),
          title: 'VueJS 3',
          description: 'VueJS 3 Documentation',
          link: 'https://v3.vuejs.org/guide/introduction.html',
        },
        {
          id: uuid.v4(),
          title: 'ReactJS',
          description: 'React Documentation',
          link: 'https://reactjs.org/docs/getting-started.html',
        },
        {
          id: uuid.v4(),
          title: 'Angular',
          description: 'Angular Documentation',
          link: 'https://angular.io/docs',
        },
      ],
    };
  },
  methods: {},
  mounted() {
    //   console.log('mounted');
    console.log(this.storedResources);
  },
};
</script>

<style>
@import 'https://cdn.jsdelivr.net/npm/bulma@0.9.3/css/bulma.min.css';
</style>