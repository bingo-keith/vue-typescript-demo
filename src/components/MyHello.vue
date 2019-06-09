<template>
  <div>
    <div class="my-test">this is my components</div>
    <div>{{testMixinArg}}</div>
    <HelloWorld></HelloWorld>
    <Children test="父组件的属性"></Children>
    <label>
      双向数据绑定：
      <input type="text" placeholder="请输入姓名" v-model="userName">
    </label>
    <br>
    <label>双向数据绑定：{{userName}}</label>
    <p @click="handleClick">{{text1}}</p>
  </div>
</template>

<script lang="ts">
import Vue from "Vue";
// import Component from "vue-class-component";
import { Component, Model } from "vue-property-decorator";
import HelloWorld from "@/components/HelloWorld";
import TestMixin from "@/mixins/test-mixin";
import Children from "@/components/Children";

@Component({
  components: {
    HelloWorld,
    Children
  },
  mixins: [TestMixin]
})
export default class MyHello extends Vue {
  @Model("input") userName: String;
  text1: String = "text1111432545";

  mounted() {
    console.log("test my Hello!!");
  }

  handleClick(e) {
    console.log(e.target.innerHTML);
  }
}
</script>

<style scope>
.my-test {
  color: red;
}
</style>
