<template>
  <div class="card has-background-dark has-text-primary-light">
    <div class="card-content">
      <div class="media-content">
        <p class="title is-4 has-text-primary-light">{{ title }}</p>
      </div>

      <div class="content">
        {{ description }}
      </div>
    </div>
    <footer class="card-footer">
      <a
        v-bind:href="link"
        class="card-footer-item has-background-link-dark has-text-white"
        >View Resource</a
      >
      <a
        href="#"
        class="card-footer-item has-background-danger-dark has-text-white"
        >Delete</a
      >
    </footer>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      required: true,
    },
  },
};
</script>

<style scoped>
.card {
  margin-bottom: 20px;
  max-width: 40%;
}
</style>