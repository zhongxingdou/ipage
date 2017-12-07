<style lang="postcss" scoped>
</style>

<template>
  <input :class="classNames" :style="style" :name="name" :type="type" />
</template>

<script>
import Element from '../base/Element';

export default {
  extends: Element,

  name: 'input',

  props: {
    name: String,
    type: String,
  },

  data() {
    return {};
  },

  methods: {
    renderHTML() {
      return `<input title="${this.title}" class="${this.getClassNames()}" style="${this.getStyle()}" ${this.getAttributes()} name="${this.name}" type="${this.type}" />`;
    },
  },
};
</script>
