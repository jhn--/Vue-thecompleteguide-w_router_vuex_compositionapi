<template>
  <section class="hero is-link">
    <div class="hero-body">
      <p class="title">
        {{ heading }}
      </p>
      <!-- <p class="subtitle">
      Link subtitle
    </p> -->
    </div>
  </section>
</template>

<script>
export default {
  props: {
    heading: {
      type: String,
      required: true,
    },
  },
};
</script>

<style>
</style>