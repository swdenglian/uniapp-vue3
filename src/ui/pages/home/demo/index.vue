<script setup lang="ts">
import { Navigate } from '@/shared'

function goBack() {
  Navigate.back()
}
</script>

<template>
  <view class="content">
    <uni-badge text="1" />
    <image class="logo" src="/static/logo.png" />
    <view class="text-area">
      <text class="title">
        HomeDemo Page
      </text>
    </view>
    <button @click="goBack">
      back
    </button>
  </view>
</template>

<style>
.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.logo {
  width: 200rpx;
  height: 200rpx;
  margin: 200rpx auto 50rpx;
}

.text-area {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 36rpx;
  color: #8f8f94;
}
</style>
