<template>
	<view>
		<view>
			<uni-nav-bar fixed="true" statusBar="true">
				<view style="margin: 0 auto; font-size: 16px;">发现</view>
				<view slot="left">
					<uni-icons type="refreshempty" size="25" @click=""></uni-icons>
				</view>
				<view slot="right" style="margin-left:30px;">
					<uni-icons type="home" size="25"></uni-icons>
				</view>
			</uni-nav-bar>
		</view>
		<view style="background-color: #FFFFFF;">
			<uni-grid :column="2" :square="false">
				<navigator url="/pages/find/shangchuan" hover-stay-time="100">
					<uni-grid-item>
						<view class="but">
							<uni-icons type="plusempty" size="26"></uni-icons>
							<text style="margin-left: 8px;font-size: 18px;">发布</text>
						</view>
					</uni-grid-item>
				</navigator>
				<navigator url="" hover-stay-time="100">
					<uni-grid-item>
						<view class="but">
							<uni-icons type="person" size="26"></uni-icons>
							<text style="margin-left: 8px;font-size: 18px;">我的</text>
						</view>
					</uni-grid-item>
				</navigator>
			</uni-grid>
		</view>
		<view>
			<luntan></luntan>
		</view>
	</view>
</template>

<script>
	import luntan from "../../components/luntan/luntan.vue"
	export default {
		name:"find",
	    data() {
	        return {
	            text: 'uni-app'
	        }
	    },
		methods:{
			// shauxin(){
			// 	this.$emit()
			// }
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
		mounted:{
			luntan,
		}
	}
</script>

<style scoped>
	.but{
		width: 170px;
		height: 60px;
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
	}
</style>
