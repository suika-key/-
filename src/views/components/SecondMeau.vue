<template>
  <div class="main_left_slider">
    <div class="main_left_slider_header"><user-outlined />专业选择</div>
    <div class="main_left_slider_content">
      <div>
        <user-outlined />
        <span>{{secondArr[0]}}</span>
      </div>
      <div>
        <user-outlined />
        <span>{{secondArr[1]}}</span>
      </div>
      <div>
        <user-outlined />
        <span>{{secondArr[2]}}</span>
      </div>
      <div>
        <user-outlined />
        <span>{{secondArr[3]}}</span>
      </div>
    </div>
  </div>
</template>

<script setup lang='ts'>
import { BellOutlined, UnorderedListOutlined, UserOutlined } from '@ant-design/icons-vue'

let { secondArr } = defineProps(['secondArr'])
console.log(secondArr)
</script>

<style scoped>
.main_left_slider {
  width: 224px;
  height: 100%;
  background-color: white;
  border-right: 1px solid rgb(187, 187, 187);
  border-left: 1px solid rgb(187, 187, 187);
}
.main_left_slider_header {
  height: 49px;
  font-size: 20px;
  line-height: 49px;
  border-bottom: 1px solid;
  padding-left: 30px;
  border-color: rgb(187, 187, 187);
}
.main_left_slider_content {
  padding-left: 30px;
}
.main_left_slider_content div {
  height: 49px;
  line-height: 49px;
}
</style>