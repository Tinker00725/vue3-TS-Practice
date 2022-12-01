<template>
    <div class="loginContainer">
     <el-card class="box-card">
        <template #header>
      <div class="card-header">
        <span>登录</span>
      </div>
    </template>
  <el-form
    ref="ruleFormRef"
    :model="ruleForm"
    status-icon
    :rules="rules"
    label-width="120px"
    class="demo-ruleForm"
  >
    <el-form-item label="账号" prop="account">
      <el-input v-model="ruleForm.account" type="text" autocomplete="off" />
    </el-form-item>
    <el-form-item label="密码" prop="password">
      <el-input
        v-model="ruleForm.password"
        type="password"
        autocomplete="off"
      />
    </el-form-item>
    <el-form-item>
      <el-button type="primary" @click="submitForm(ruleFormRef)" class="loginButton"
        >登录</el-button
      >
    </el-form-item>
  </el-form>
</el-card>
</div>
</template>

<script setup lang="ts">
import { reactive } from 'vue';

const ruleForm = reactive({
    account:'',
    password:''
})

const rules = reactive({
  account:[{}]
})

function submitForm():void{

}
</script>

<style >
.loginContainer{
    width: 100%;
    height: 100%;
    background:url('@/assets/imges/背景图片.webp');
    background-size: cover;
}
.card-header {
  display: flex;
  justify-content: center;
  align-items: center;
}
.box-card {
  width: 480px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%,-50%);
}
.loginButton{
  width: 120px;
  margin: auto;
  transform: translateX(-40%);
}
</style>