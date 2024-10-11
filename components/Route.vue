<template>
    <div></div>
</template>

<script setup lang="ts">
const currentRoute = useRoute();

const routeName = currentRoute.name;
console.log('当前页面路由的name:', routeName);

</script>
