<!-- 编辑布局时渲染用 -->
<style lang="postcss" scoped>

</style>

<!-- 编辑布局时渲染用 -->
<template>
  <div :class="classNames" :style="style"></div>
</template>

<script>
export default {
  name: 'element',

  /* 组件的可配置属性 */
  props: {
    classNames: {
      group: 'style',
      type: Array,
      default() {
        return [];
      },
    },
    title: {
      group: 'html',
      type: String,
    },
    style: {
      group: 'style',
      type: Object,
      default() {
        return {};
      },
    },
    attributes: {
      group: 'attribute',
      type: Object,
      default() {
        return {};
      },
    },
  },

  data() {
    return {
      // 标识单个元素
      tagName: '',
      // 图标代表这类元素
      tagIcon: 'element',
      // 是否可编辑
      editable: true,
      // 是否可包含其他元素
      isContainer: false,
    };
  },

  methods: {
    getStyle() {
      return Object.entries(this.style).map(([k, v]) => `${k}: ${v}`).join(';');
    },
    getClassNames() {
      return this.classNames.join(' ');
    },
    getAttributes() {
      return Object.entries(this.attributes).map(([k, v]) => `${k}="${v}"`).join(' ');
    },
    renderHTML() {
      return `<div title="${this.title}" class="${this.getClassNames()}" style="${this.getStyle()}" ${this.getAttributes()}></div>`;
    },
  },
};
</script>
