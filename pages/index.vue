<template>
  <div class="m-2 flex flex-col items-center justify-center gap-2">
    <p>defult</p>
    <Avatar img="woman.jpg" />

    <p>square</p>
    <Avatar img="woman.jpg" square />

    <p>border</p>
    <Avatar img="woman.jpg" border />

    <p>border square</p>
    <Avatar img="woman.jpg" square border />

    <p>icon</p>
    <Avatar />

    <p>initials</p>
    <Avatar initials="CS" />

    <p>dot</p>
    <Avatar img="woman.jpg" dot />
  </div>
</template>

<script setup>
const alert = ref("Simple text information.");
</script>
