<script setup>
import HomeButton from "../components/HomeButton.vue";
import HomeFuncBoard from "../components/HomeFuncBoard.vue";
import InputComponent from "../components/InputComponent.vue";
import { useFuncCate } from "../stores/funcCate";
import { useChat } from "../stores/chat";
import { useStyle } from "../stores/style";
import { ElNotification } from "element-plus";
import { storeToRefs } from "pinia";

const funcCate = useFuncCate();
const chat = useChat();
const style = useStyle();
const { showNum } = storeToRefs(style);
</script>

<template>
  <div class="inp_box">
    <InputComponent
      :height="30"
      :width="97"
      @keyup.enter.native="funcCate.cate = chat.say"
      placeholder="搜索场景名"
    ></InputComponent>
  </div>
  <HomeButton></HomeButton>
  <HomeFuncBoard></HomeFuncBoard>
</template>

<style lang="scss" scoped>
.inp_box {
  height: 50px;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 15px;
}
</style>
