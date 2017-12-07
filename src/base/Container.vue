<style lang="postcss" scoped>
  div{
    width: 300px;
    height: 100px;
    border: 1px dashed blue;
  }
</style>

<template>
  <div :class="classNames" :style="style"></div>
</template>

<script>
import Element from './Element';

export default {
  name: 'container',

  extends: Element,

  data() {
    return {
      isContainer: true,
      includeTags: [],
      excludeTags: [],
    };
  },

  methods: {
    canContain(tagName) {
      if (this.excludeTags.includes(tagName)) return false;
      if (this.includeTags.length === 0) return true;
      return this.includeTags.includes(tagName);
    },
    renderChildrenHTML() {
      return this.$children.map(child => child.renderHTML()).join('');
    },
    renderHTML() {
      return `<div title="${this.title}" class="${this.getClassNames()}" style="${this.getStyle()}" ${this.getAttributes()}>${this.renderChildrenHTML()}</div>`;
    },
  },
};
</script>
