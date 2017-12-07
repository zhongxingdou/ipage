<style>
.container-fluid{
  height: 100%;
}
.row{
  height: 100%;
  >div{
    display: flex;
    flex-direction: column;
  }
}
</style>

<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-3">
        <component-list></component-list></div>
      <div class="col-md-6">
        <layout-editor></layout-editor></div>
      <div class="col-md-3">
        <properties-editor></properties-editor></div>
    </div>
  </div>
</template>

<script>
import ComponentList from './ComponentList';
import LayoutEditor from './LayoutEditor';
import PropertiesEditor from './PropertiesEditor';

export default {
  components: {
    ComponentList,
    LayoutEditor,
    PropertiesEditor,
  },
};
</script>
