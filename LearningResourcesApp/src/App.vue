<template>
  <ul>
    <li v-for="resource in storedResources" :key="resource.id">
      {{ resource.id }}
      {{ resource.title }}
      {{ resource.description }}
      {{ resource.link }}
    </li>
  </ul>
</template>

<script>
import { uuid } from 'vue-uuid';

export default {
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
</style>