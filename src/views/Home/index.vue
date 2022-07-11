<template>
<div>

    <AppHeaader/>
    <HomeTabs/>
    <HomeSwiper/>
    <HomeVideoList/>
    <router-link to="/video/index">视频页</router-link>
</div>
    
</template>
<script setup lang="ts">
import AppHeaader from "@/components/home-header.vue"
import HomeTabs from '@/components/home-tabs.vue'
import HomeSwiper from '@/components/home-swiper.vue'
import HomeVideoList from '@/components/home-video-list.vue'


</script>