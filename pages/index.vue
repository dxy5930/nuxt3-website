<template>
	<div>

		<Head>
			<Title>{{ title }}</Title>
			<Meta name="description" :content="title" />
			<!-- <Style type="text/css" children="body { background-color: green; }" /> -->
		</Head>
		<AloneBanner class="h-44 md:h-auto" :data='bannerList' />

		<!-- 新闻中心 -->
		<div class="py-1 md:py-8" style="background-color: #fff;">
			<section class="al-container">
				<div class="flex justify-between mb-6">
					<div>
						<h2 class="md:text-4xl md:mb-2" style="color: #333;font-weight: 600;">新闻中心</h2>
						<p class="hidden md:block text-xs md:text-2xl" style="font-style: italic;color: #d6dbe4;">NEWS
							CENTER</p>
					</div>
					<div class="flex items-center">
						<div class="bar"></div>
						<p class="text-xs md:text-lg text-slate-400">先锋音讯16年品质保证，值得您信赖的伙伴</p>
					</div>
				</div>
				<div class="md:flex">
					<div class="md:w-1/2 mb-8">
						<img class="rounded-lg w-full h-52 md:h-100"
							src="http://www.pioneerw.com/3.0/style/image/4.png">
					</div>
					<div class="p-1 md:w-1/2 md:ml-10">
						<ul class="news-list-ul">
							<li class="mb-5 md:mb-10" v-for="(newsItem, index) in newsList" :key="index">
								<h3>
									<Nuxt-link class="text-lg" to="/about">
										<span class="num" style="">{{ index + 1 }}</span>
										{{ newsItem.title }}
										<span class="hidden md:block"
											style="color: #999;float: right;font-weight: normal;font-size: 1rem;">{{
												newsItem.date }}</span>
									</Nuxt-link>
								</h3>
							</li>
						</ul>
					</div>
				</div>
			</section>
		</div>
		<!-- 行业解决方案 -->
		<PageSolution />
		<!-- 产品中心 -->
		<PageProduct />
	</div>
</template>

<script setup>
const title = ref('VAA先锋音讯企业官网')
const bannerList = ref([{
	title: '这是一个title',
	image: 'https://cdn-public.nio.com/www-nio-cn/cms/zh_CN/page_et5/1726136110949-1726136110311-5DFAD2383B6242CE.jpg',
	type: 2,
	video: 'https://cdn-public.nio.com/www-nio-cn/asset-migration/page_new_homepage/cdn-static/luban/nextjs/images/default-large-files/1700626256416-83086BF7A097443E.mp4',
},
{
	title: '这是一个title',
	image: 'https://cdn-public.nio.com/www-nio-cn/cms/zh_CN/page_et5/1726136110949-1726136110311-5DFAD2383B6242CE.jpg',
	type: 2,
	video: 'https://cdn-public.nio.com/www-nio-cn/asset-migration/page_new_homepage/cdn-static/mynio/nextjs/images/home/video/homepage-slider-et5-desktop.mp4',
},
{
	title: '这是一个title',
	image: 'https://cdn-public.nio.com/www-nio-cn/asset-migration/page_es6/cdn-static/mynio/cms/zh_CN/page_es6/1709284903799-topHero.image.desktop-E7DFE9580245A4F6.jpg',
	type: 2,
	video: 'https://www.nio.com/cdn-static/luban/nextjs/images/default-large-files/es6-top-hero-desktop.mp4',
},
])
const newsList = ref([{
	title: '先锋AI转写一体云录音系统',
	date: '2022-11-14'
},
{
	title: '2022年人工智能领域发展七大趋势',
	date: '2022-11-12'
},
{
	title: '先锋云录音系统助力铁路行业对讲机、售票窗口录音',
	date: '2022-11-12'
},
{
	title: '先锋音讯应邀参加  2019第四届上海国际人工智能展',
	date: '2022-11-12'
},
{
	title: '先锋音讯中标广铁集团 VAA技术融入铁路行业专网',
	date: '2022-11-12'
},
{
	title: '2022年人工智能领域发展七大趋势',
	date: '2022-11-12'
},
])
</script>

<style>
.num {
	color: #fff;
	font-weight: normal;
	padding: 2px 12px;
	font-size: 1rem;
	margin-right: 5px;
	background-color: #a9a5a5;
	border-radius: 1px;
}

.news-list-ul li:nth-child(1) .num {
	background-color: #fb0d0d;
}

.news-list-ul li:nth-child(2) .num {
	background-color: #fb9c0d;
}

.news-list-ul li:nth-child(3) .num {
	background-color: #15acd9;
}
</style>
