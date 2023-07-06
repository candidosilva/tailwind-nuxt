<template>
  <div class="relative">
    <nuxt-img
      v-if="img"
      class="h-10 w-10"
      :class="[squareAvatar, border]"
      :src="img"
      :alt="alt"
    />

    <div
      v-else-if="initials"
      class="flex h-10 w-10 items-center justify-center bg-gray-100 text-xl font-medium text-gray-600"
      :class="[squareAvatar, border]"
    >
      {{ initials }}
    </div>

    <div
      v-else
      class="h-10 w-10 rounded-full bg-gray-100"
      :class="[squareAvatar, border]"
    >
      <Icon name="mdi:account" size="40" color="gray" />
    </div>

    <span
      v-if="dot"
      class="absolute h-3.5 w-3.5 rounded-full border-2 border-white bg-red-400"
      :class="[square ? '-top-2 left-8' : 'left-7 top-0']"
    ></span>
  </div>
</template>

<script setup>
const props = defineProps({
  img: {
    type: String,
  },
  alt: {
    type: String,
  },
  square: {
    type: Boolean,
  },
  border: {
    type: Boolean,
  },
  initials: {
    type: String,
  },
  dot: {
    type: Boolean,
  },
});

const squareAvatar = computed(() => {
  if (props.square) return "rounded";
  return "rounded-full";
});

const border = computed(() => {
  if (props.border) return "ring-2 ring-blue-500";
  return "";
});
</script>
