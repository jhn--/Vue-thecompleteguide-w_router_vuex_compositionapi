<template>
  <base-dialog>
    <div class="modal-content card has-background-danger-light is-light">
      <slot name="default"> </slot>
    </div>
    <slot name="actions"> </slot>
  </base-dialog>
</template>

<script>
</script>

<style scoped>
.modal-content {
  height: 40%;
  padding: 5rem;
}
</style>