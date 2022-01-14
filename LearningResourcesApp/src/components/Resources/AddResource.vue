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
    <teleport to="body">
      <error-alert :class="{ 'is-active': isActive }">
        <template #default>
          <h3 class="is-size-3 has-text-danger">Error</h3>
          <p class="is-size-4">More than one fields are empty.</p>
          <p class="is-size-4">
            Please make sure you fill the fields with valid information.
          </p>
        </template>
        <template #actions>
          <button class="modal-close" @click="closeErrorAlert"></button>
        </template>
      </error-alert>
    </teleport>
  </div>
</template>

<script>
import ErrorAlert from '../UI/ErrorAlert.vue';
export default {
  components: { ErrorAlert },
  data() {
    return {
      resource: {
        title: '',
        description: '',
        link: '',
        logo: '',
      },
      error: false,
    };
  },
  computed: {
    isActive() {
      if (this.error === true) {
        return true;
      } else {
        return false;
      }
    },
  },
  methods: {
    addResource() {
      if (
        this.resource.title.trim() === '' ||
        this.resource.description.trim() === '' ||
        this.resource.link.trim() === ''
      ) {
        this.error = true;
        // return false;
      } else {
        this.$emit('add-resource', this.resource);
        this.resource = {
          title: '',
          description: '',
          link: '',
          logo: '',
        };
      }
    },
    closeErrorAlert() {
      this.error = false;
    },
  },
};
</script>

<style>
</style>