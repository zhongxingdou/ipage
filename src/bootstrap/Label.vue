<style lang="postcss" scoped>
</style>

<template>
  <label :for="for" :class="classNames" :style="style">{{label}}
    <component :is="controlName"></component>
  </label>
</template>

<script>
import Container from '../base/Container';

export default {
  extends: Container,

  name: 'label',

  props: {
    label: String,
    for: String,
  },

  data() {
    return {
      includeTags: ['input', 'select', 'textarea'],
      controlName: '',
    };
  },

  methods: {
    renderHTML() {
      return `<label title="${this.title}" class="${this.getClassNames()}" style="${this.getStyle()}" ${this.getAttributes()}>${this.renderChildrenHTML()}</label>`;
    },
    canContain() {
      // 只可以包含一个子组件
      if (this.$children.length) return false;

      return Container.methods.canContain.call(this);
    },
  },
};
</script>
