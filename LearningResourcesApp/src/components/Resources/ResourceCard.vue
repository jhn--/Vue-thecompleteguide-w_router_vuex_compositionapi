<template>
  <li class="block">
    <base-card class="has-background-dark has-text-primary-light">
      <div class="card-content">
        <div class="media-content">
          <p class="title is-4 has-text-primary-light">
            {{ title }}
            <span class="icon">
              <ion-icon size="large" :name="logo"></ion-icon>
            </span>
          </p>
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
    </base-card>
  </li>
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
    logo: {
      type: String,
      required: false,
    },
  },
};
</script>

<style>
</style>