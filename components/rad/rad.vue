<template>
	<view>
		<uni-grid :column="4" :showBorder="false" :highlight="true">
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangmianxingyishutubiao"></view>
					<text>经方学社</text>
				</view>
			</uni-grid-item>
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfanghuodongx"></view>
					<text>活动报名</text>
				</view>
			</uni-grid-item>
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangmingshi"></view>
					<text>名师榜</text>
				</view>
			</uni-grid-item>
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangdaohang"></view>
					<text>课程导航</text>
				</view>
			</uni-grid-item>
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangjingpinkecheng"></view>
					<text>精品课</text>
				</view>
			</uni-grid-item>
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangyinpin"></view>
					<text>音频课</text>
				</view>
			</uni-grid-item>
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangwoyaozhibo"></view>
					<text>直播回顾</text>
				</view>
			</uni-grid-item>
			<uni-grid-item>
				<view class="juzhong">
					<view class="t-icon t-icon-jiingfangquanbu"></view>
					<text>全部课程</text>
				</view>
			</uni-grid-item>
		</uni-grid>
	</view>
</template>

<script>
	export default {
		name:'rad'
	}
</script>

<style scoped>
	.t-icon{
		width: 40px;
		height: 40px;
	}
	
	.juzhong{
		display: flex;
		margin: 10px;
		flex-direction: column;
		align-items: center;
	}
</style>
