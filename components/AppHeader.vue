<template>
	<header :class="['header', { 'header-scrolled': isScrolled }]">
		<div>
			<img class="h-16" src="https://youjia.cdn.bcebos.com/youjia_logo/2024-4/1711956519022/c3af31d8fa84.png"
				alt="">
		</div>
		<AloneNavBar :data="navList" />
	</header>
	<!-- <div class="header-white"></div> -->
</template>

<script setup>
import { useScroll } from '@/composables/useScroll';

const navIndex = ref(0);
const navList = ref([
	{ name: '首页', link: '/' },
	{ name: '产品中心', link: '/product' },
	{
		name: '解决方案', link: '/solution', children: [
			{ name: '银行解决方案', link: '/solution/bank' },
			{ name: '证券解决方案', link: '/solution/bank' },
			{ name: '高铁解决方案', link: '/solution/bank' },
		]
	},
	{ name: '用户案例', link: '/example' },
	{ name: '新闻中心', link: '/news' },
	{ name: '关于我们', link: '/about' },
]);

const { isScrolled } = useScroll(50);
</script>

<style lang="scss">
.header {
	position: relative;
	display: flex;
	justify-content: space-between;
	align-items: center;
	background-color: rgba($color: #000000, $alpha: 0.2);
	z-index: 999;
	padding: 0 10%;
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: $header-height;
	transition: background-color 0.5s ease;
}

.header-scrolled {
	background-color: white;
}

.header-white {
	height: $header-height
}
</style>
