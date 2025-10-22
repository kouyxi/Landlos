<script setup>
const props = defineProps({
  isFocus: {
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <div class="button" :class="{ 'button-focus': isFocus }">
    <slot />
  </div>
</template>

<style>
@font-face {
  font-family: "minecraftia";
  src: url("/fonts/Minecraftia-Regular.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}

.button {
  border: 1px solid var(--white);
  border-radius: 4px;
  background-color: none;
  color: var(--white);
  padding: 8px 18px;
  margin: 0;
  cursor: pointer;
  font-size: 13px;
  white-space: nowrap;
  font-family: "minecraftia", monospace;
  transition: all 0.1s ease;
  user-select: none;
}

.button:hover {
  transform: translate(-2px, -2px);
  box-shadow: 4px 4px var(--white);
}

.button:active {
  transform: translate(3px, 3px);
  box-shadow: 0px 0px black;
}

.button-focus {
  background: var(--white);
  color: var(--black);
  border: 1px solid var(--white);
}

.button-focus:hover {
  background: linear-gradient(135deg, var(--red), var(--dark-red));
  color: var(--white);
  transform: translate(-2px, -2px);
}

.button-focus:active {
  transform: translate(3px, 3px);
  box-shadow: 0px 0px black;
}
</style>
