<template>
  <div>
    <div style="text-align: center;">
      <div class="site-title"> Title</div>
      <span v-if="!preview">
        <button class="btn btn-outline-primary" @click="addTitleGridItem"> H1 </button>
        <button class="btn btn-outline-primary" @click="addContentGridItem"> Content </button>
      </span>
      <button class="btn btn-outline-primary" @click="disableGrid"> 
        <span v-if="preview"> Edit </span>
        <span v-else="preview"> Preview </span>
      </button>
    </div>
    <hr>
    <grid-layout :layout="getResources"
      :col-num="12" :row-height="30" :is-draggable="isDraggable" :is-resizable="isResizable"
      :is-mirrored="false" :vertical-compact="true" :margin="[5, 5]"
      :use-css-transforms="true">
      <grid-item v-for="(item, index) in getResources" :key="index" :class="{ 'editMode' : !preview }"
      :autoSize="true" :x="item.x" :y="item.y" :w="item.w" :h="item.h" :i="item.i">

        <div v-if="!preview" @click="removeItem({key: index})" style="position: absolute; bottom: 0px; left: 4px;">
          <i class="fa fa-trash" aria-hidden="true"></i>
        </div> 
        


      </grid-item>
    </grid-layout>
  </div>
</template>
<script>


import { GridLayout, GridItem } from 'vue-grid-layout'
export default {
  name: 'gridview',
  components: { GridLayout, GridItem },
  data () {
    return {
      isDraggable: false,
      isResizable: false,
      preview: true,
      contenteditable: false
    }
  },


    disableGrid () {
      this.isDraggable = !this.isDraggable
      this.isResizable = !this.isResizable
      this.preview = !this.preview
      this.contenteditable = !this.contenteditable
    }
  }

</script>
<style>
.editMode {
  background-color: #fafafa;
  border-radius: 5px;
}
.site-title {
  font-family: 'Lilita One', cursive;
  font-size: 50px;
  color: #F48FB1;
  text-align: center;
}
.heading1 { 
  font-family: 'Crushed', cursive;
  font-size: 35px;
  border: none;
  color: #2196F3;
}
.heading2 { 
  font-family: 'Patrick Hand', cursive;
  font-size: 20px;
  border: none;
  color: #3096f3;
  background-color: #FFF9C4;
  width: 100%;
  padding: 10px 5px;
}
.heading3 {
  font-family: 'Homemade Apple', cursive;
  font-size: 20px;
  border: none;
  color: #66d2b3;
  padding: 0 7px;
}
.content {
  font-family: 'Patrick Hand', cursive;
  font-size: 20px;
  color: #2196F3;
}
</style>