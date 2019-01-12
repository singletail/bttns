<template>
 <div class="container">
    <div style="width: 930px; margin: 0 auto;">
      <GridView></GridView>
      <div style="background: #FCE4EC; text-align: center; padding: 50px; margin: 50px 0; border-radius: 5px;">
        <h4> Hi </h4>
      </div>
    </div>
  </div>
</template>

<script>
import GridView from './GridView.vue';

export default {
  name: 'Breadboard',
  components: {
    GridView
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
