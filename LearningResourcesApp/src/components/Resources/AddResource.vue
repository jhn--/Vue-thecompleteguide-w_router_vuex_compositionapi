<template>
  <div class="container is-max-desktop box">
    <h3 class="title is-3">Add Resource</h3>
    <form action="" method="POST" @submit.prevent="addResource">
      <div class="field">
        <label class="label">Title</label>
        <div class="control">
          <input
            class="input"
            type="text"
            placeholder="Text input"
            v-model="resource.title"
          />
        </div>
      </div>
      <div class="field">
        <label class="label">Link</label>
        <div class="control">
          <input
            class="input"
            type="text"
            placeholder="Text input"
            v-model="resource.link"
          />
        </div>
      </div>
      <div class="field">
        <label class="label">Description</label>
        <div class="control">
          <textarea
            class="textarea"
            placeholder="Textarea"
            v-model="resource.description"
          ></textarea>
        </div>
        <div class="field">
          <label class="label">ionicon Name</label>
          <div class="control">
            <input
              class="input"
              type="text"
              placeholder="Text input"
              v-model="resource.logo"
            />
          </div>
        </div>
      </div>
      <div class="control">
        <button class="button is-link">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      resource: {
        title: '',
        description: '',
        link: '',
        logo: '',
      },
    };
  },
  methods: {
    addResource() {
      //   console.log(this.resource);
      this.$emit('add-resource', this.resource);
      this.resource = {
        title: '',
        description: '',
        link: '',
        logo: '',
      };
    },
  },
};
</script>

<style>
</style>