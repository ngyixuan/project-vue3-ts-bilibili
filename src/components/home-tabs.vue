<template>

<van-tabs :active="active">
<van-tab v-for="item in list" :key="item.id" :title="item.text"></van-tab>
</van-tabs>


<!-- <van-tabs :active="active">
<van-tab title="标签 1">内容 1</van-tab>
<van-tab title="标签 2">内容 2</van-tab>
<van-tab title="标签 3">内容 3</van-tab>
<van-tab title="标签 4">内容 4</van-tab>
</van-tabs> -->
</template>
<script setup lang="ts">
// ref 函数用于定义模板中使用的响应式数据，相当于 Vue2 的 data
import { ref } from 'vue'
import axios from 'axios'
// active 表示当前选中标签的下标为 0
const active = ref(0)
// 频道数据， <INavItem[]> 表示 list 数据为数组，数组的每一项需要复合 INavItem 接口的格式
// TypeScript 好处：模板中使用 list 和 item 的时候，鼠标移入有类型提醒
const list = ref<INavItem[]>([])

interface INavItem {
 id: string
 text: string
}

axios({
    url:'/navList',
    method:'get',


}).then(res => {
 console.log('获取频道数据', res.data)
 list.value = res.data.result
})
</script>