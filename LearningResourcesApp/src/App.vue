<template>
  <TheHeading :heading="heading" />
  <TheNavbar @select-tab="selectTab" />
  <keep-alive>
    <component
      :is="selectedTab"
      :resources="storedResources"
      @add-resource="addNewResource"
    />
  </keep-alive>
</template>

<script>
import { uuid } from 'vue-uuid';

import ResourceList from './components/Resources/ResourceList.vue';
import AddResource from './components/Resources/AddResource.vue';
import TheHeading from './components/layouts/TheHeading.vue';
import TheNavbar from './components/layouts/TheNavbar.vue';

export default {
  components: {
    ResourceList,
    AddResource,
    TheHeading,
    TheNavbar,
  },
  data() {
    return {
      heading: 'Learning Resources',
      selectedTab: 'resource-list',
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
  provide() {
    return {
      deleteResource: this.deleteExistingResource,
    };
  },
  methods: {
    selectTab(cmp) {
      this.selectedTab = cmp;
    },
    addNewResource(resource) {
      console.log(resource);
      resource.id = uuid.v4();
      this.storedResources.push(resource);
      this.selectTab('resource-list');
    },
    deleteExistingResource(id) {
      // console.log(id);
      this.storedResources = this.storedResources.filter(
        (resource) => resource.id !== id
      );
    },
  },
  mounted() {
    //   console.log('mounted');
    console.log(this.storedResources);
  },
};
</script>

<style>
@import 'https://cdn.jsdelivr.net/npm/bulma@0.9.3/css/bulma.min.css';
</style>