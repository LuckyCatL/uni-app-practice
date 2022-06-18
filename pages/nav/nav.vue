<template>
	<view class="container">
		<view>
		<uni-group :mode="card" top="20">
			<navigator :hover-stay-time="100">
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangzhongyike"></view>
					<view class="zi">经方大师</view>
					<uni-icons type='right' class="jiantou1" style="color: #969696;"></uni-icons>
				</view>
			</navigator>
			<hr>
			<navigator :hover-stay-time="100">
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfang37search"></view>
					<view class="zi">伤寒检索</view>
					<uni-icons type='right' class="jiantou1" style="color: #969696;"></uni-icons>
				</view>
			</navigator>
		</uni-group>
		<uni-group :mode="card" top="20">
			<navigator :hover-stay-time="100">
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangzu6555"></view>
					<view class="zi">医案</view>
					<uni-icons type='right' class="jiantou2" style="color: #969696;"></uni-icons>
				</view>
			</navigator>
			<hr>
			<navigator :hover-stay-time="100">
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfanga-shushuji"></view>
					<view class="zi">医书</view>
					<uni-icons type='right' class="jiantou2" style="color: #969696;"></uni-icons>
				</view>
			</navigator>
			<hr>
			<navigator :hover-stay-time="100">
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangshu"></view>
					<view class="zi">辞典</view>
					<uni-icons type='right' class="jiantou2" style="color: #969696;"></uni-icons>
				</view>
			</navigator>
		</uni-group>
		</view>
		<view>
			<uni-fab @fabClick="showDrawer()"></uni-fab>
			<uni-drawer ref="showRight" mode="right" :mask-click="true">
				
			</uni-drawer>
		</view>
	</view>
</template>

<script>
	
	export default {
		data(){
			return{
				// card:'card',
				color1:'#CFB06E'
			}
		},
		methods:{
			showDrawer() {
			                this.$refs.showRight.open();
			},
			
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
	@import "@/static/iconfir/iconfont.css";
	.container {
		padding-left: 10px;
		padding-right: 10px;
		font-size: 14px;
		line-height: 24px;
	}
	.t-icon{
		height: 40px;
		width: 40px;
	}
	.juzhong{
		height: 60px;
		display: flex;
		flex-direction: row;
		align-items: center;
		margin: 2px;
		
		/* padding-left: 10px; */
	}
	.zi{
		margin-left: 20px; 
		font-size:20px;
		font-weight: bolder;
		color: #969696;
	}
	.jiantou1{
		margin-left: 150px; 
		
	}
	.jiantou2{
		margin-left: 190px;
		
	}
</style>
