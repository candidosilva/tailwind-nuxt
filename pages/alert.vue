<template>
  <div class="m-10">
    <Alert type="success" :text="alert" closable />
    <Alert type="info" :text="alert" class="mt-6" closable />
    <Alert type="warning" :text="alert" class="mt-6" closable />
    <Alert type="error" :text="alert" class="mt-6" closable />
    <Alert :text="alert" class="mt-6" closable />
  </div>
</template>

<script setup>
const alert = ref("Simple text information.");
</script>
