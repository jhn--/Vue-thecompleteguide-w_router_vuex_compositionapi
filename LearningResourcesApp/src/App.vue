<template>
  <TheHeading :heading="heading" />
  <ResourceList :resources="storedResources" />
</template>

<script>
import { uuid } from 'vue-uuid';

import ResourceList from './components/Resources/ResourceList.vue';
import TheHeading from './components/layouts/TheHeading.vue';

export default {
  components: {
    ResourceList,
    TheHeading,
  },
  data() {
    return {
      heading: 'Learning Resources',
      storedResources: [
        {
          id: uuid.v4(),
          title: 'VueJS 3',
          description: 'VueJS 3 Documentation',
          link: 'https://v3.vuejs.org/guide/introduction.html',
          logo: 'logo-vue',
        },
        {
          id: uuid.v4(),
          title: 'ReactJS',
          description: 'React Documentation',
          link: 'https://reactjs.org/docs/getting-started.html',
          logo: 'logo-react',
        },
        {
          id: uuid.v4(),
          title: 'Angular',
          description: 'Angular Documentation',
          link: 'https://angular.io/docs',
          logo: 'logo-angular',
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