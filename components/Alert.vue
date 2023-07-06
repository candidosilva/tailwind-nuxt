<template>
  <div class="flex rounded-lg p-4" :class="[colors, hidden]">
    <Icon :name="iconValue" size="20" class="mr-3" v-show="type" />

    <div class="text-sm font-medium">
      {{ text }}
    </div>

    <button
      v-if="closable"
      type="button"
      class="-mx-1.5 -my-1.5 ml-auto inline-flex h-8 w-8 rounded-lg p-1.5"
      :class="hover[type]"
      @click="close = true"
    >
      <Icon name="mdi:close" size="20" />
    </button>
  </div>
</template>

<script setup>
const props = defineProps({
  text: {
    type: String,
  },
  type: {
    type: String,
  },
  closable: {
    type: Boolean,
  },
});

const close = ref(false);

const bgColorTypes = {
  undefined: "bg-gray-50",
  success: "bg-green-50",
  info: "bg-blue-50",
  warning: "bg-yellow-50",
  error: "bg-red-50",
};

const textColor = {
  undefined: "text-gray-800",
  success: "text-green-800",
  info: "text-blue-800",
  warning: "text-yellow-800",
  error: "text-red-800",
};

const icon = {
  undefined: "",
  success: "success",
  info: "information",
  warning: "warning",
  error: "error",
};

const hover = {
  undefined: "hover:bg-gray-200",
  success: "hover:bg-green-200",
  info: "hover:bg-blue-200",
  warning: "hover:bg-yellow-200",
  error: "hover:bg-red-200",
};

const colors = computed(() => {
  return `${bgColorTypes[props.type]} ${textColor[props.type]} `;
});
const hidden = computed(() => {
  if (close.value) return "hidden";
  return "";
});

const iconValue = computed(() => {
  if (props.type !== undefined) return `mdi:${icon[props.type]}`;
  return "";
});
</script>
