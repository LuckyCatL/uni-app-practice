<template>
	<view class="container">
		<uni-fab
			:pattern="pattern"
			:content="content"
			:horizontal="horizontal"
			:vertical="vertical"
			:direction="direction"
			@trigger="trigger"
			:popMenu="true"
		></uni-fab>
		
		<view class="">
			<uni-search-bar @confirm="search" @input="input" :bgColor="col" :radius="radius"></uni-search-bar>
		</view>
		<view>
			<uni-swiper-dot :info="info" :current="current" field="content" :mode="mode">
			    <swiper class="swiper-box" @change="change">
			        <swiper-item v-for="(item ,index) in info" :key="index">
			            <view>
			                <image  :src="item.url" mode="aspectFill" style="width: 100%;"/>
			            </view>
			        </swiper-item>
			    </swiper>
			</uni-swiper-dot>
		</view>
		<br>
		<view>
			<rad></rad>
		</view>
		<br>
		<view>
			<fenzu></fenzu>
			<fenzu></fenzu>
			<fenzu></fenzu>
		</view>
	</view>
</template>

<script>
	import rad from '../../components/rad/rad.vue'
	import fenzu from '../../components/rad/fenzu.vue'
	export default {
		data() {
			return {
				href: 'https://uniapp.dcloud.io/component/README?id=uniui',
				content:[
				{
					iconPath: '../../static/icon/bubble.png',
					selectedIconPath: '../../static/icon/bubble1.png',
					text: '动态',
					active: false
				},
				{
					iconPath: '',
					selectedIconPath: '',
					text: '评论',
					active: false
				},
				{
					iconPath: '',
					selectedIconPath: '',
					text: '反馈',
					active: false
				}
				],
				direction:'vertical',
				
				info: [{
				            content: '内容 A',
							url:'../../static/img/1.png'
				        }, 
						{
				            content: '内容 B',
							url:'../../static/img/2.png'
				        }, 
						{
				            content: '内容 C',
							url:'../../static/img/3.png'
						}],
				        current: 0,
				        mode: 'round',
						col:'#FFFFFF',
						radius:'20',
						pattern:{
							color:'#282C34',
							selectedColor:'#FFFFFF',
							backgroundColor: '#fff',
							// buttonColor:'#41A863'
						},
			}
			
		},
		methods: {
			change(e) {
			            this.current = e.detail.current;
			        }
		},
		
		components:{
			rad,
			fenzu
		},
		//下拉刷新
		onLoad: function (options) {
		    setTimeout(function () {
		        console.log('start pulldown');
		    }, 1000);
		    uni.startPullDownRefresh();
		},
		onPullDownRefresh() {
		    console.log('refresh');
		    setTimeout(function () {
		        uni.stopPullDownRefresh();
		    }, 1000);
		},
	}
</script>

<style scoped>
	.container {
		padding-left: 10px;
		padding-right: 10px;
		font-size: 14px;
		line-height: 24px;
	}
	.top{
		display: flex;
		flex-direction: column;
		
	}
</style>
