<template>
	<view>
		<uni-nav-bar fixed="true" statusBar="true">
			<view style="margin: 0 auto; font-size: 16px;">我的</view>
			<view slot="left">
				<uni-icons type="scan" size="25" @click="saoma()"></uni-icons>
			</view>
			<view slot="right" style="margin-left:30px;">
				<uni-icons type="email" size="25"></uni-icons>
			</view>
		</uni-nav-bar>
		<view>
			<uni-group title="个人信息" top="0">
				<view>
				</view>
			</uni-group>
			<uni-group title="课程管理" mode="">
				<uni-grid :column="4" :showBorder="false"  :square="false">
				    <uni-grid-item>
						<view class="juzhong">
							<uni-icons customPrefix="iconfont" type="icon-weibiaoti--" size="26"></uni-icons>
							<text class="zi">课程导航</text>
						</view>
				    </uni-grid-item>
				    <uni-grid-item>
				        <view class="juzhong">
				        	<uni-icons customPrefix="iconfont" type="icon-packet" size="26"></uni-icons>
				        	<text class="zi">已购买</text>
				        </view>
				    </uni-grid-item>
				    <uni-grid-item>
				        <view class="juzhong">
				        	<uni-icons customPrefix="iconfont" type="icon-xiazai_yixiazai" size="26"></uni-icons>
				        	<text class="zi">已下载</text>
				        </view>
				    </uni-grid-item>
				    <uni-grid-item>
				        <view class="juzhong">
				        	<uni-icons customPrefix="iconfont" type="icon-yishoucang_huaban1" size="26"></uni-icons>
				        	<text class="zi">已收藏</text>
				        </view>
				    </uni-grid-item>
				    <uni-grid-item>
				        <view class="juzhong">
				        	<uni-icons customPrefix="iconfont" type="icon-yidingyue" size="26"></uni-icons>
				        	<text class="zi">已订阅</text>
				        </view>
				    </uni-grid-item>
				    <uni-grid-item>
				        <view class="juzhong">
				        	<uni-icons customPrefix="iconfont" type="icon-bofangjilu" size="26"></uni-icons>
				        	<text class="zi">播放记录</text>
				        </view>
				    </uni-grid-item>
					<uni-grid-item>
					    <view class="juzhong">
					    	<uni-icons customPrefix="iconfont" type="icon-credit_management" size="26"></uni-icons>
					    	<text class="zi">学分管理</text>
					    </view>
					</uni-grid-item>
					<uni-grid-item>
					    <view class="juzhong">
					    	<uni-icons customPrefix="iconfont" type="icon-xuexi" size="26"></uni-icons>
					    	<text class="zi">学习</text>
					    </view>
					</uni-grid-item>
				</uni-grid>
			</uni-group>
			<uni-group>
				<view>
					<navigator :hover-stay-time="100">
						<view class="juzhong1">
							<uni-icons customPrefix="iconfont" type="icon-kefu" size="20"></uni-icons>
							<text class="zi1">在线客服</text>
						</view>
					</navigator>
					<hr>
					<navigator :hover-stay-time="100">
						<view class="juzhong1">
							<uni-icons customPrefix="iconfont" type="icon-wenti" size="20"></uni-icons>
							<text class="zi1">常见问题</text>
						</view>
					</navigator>
				</view>
			</uni-group>
			<uni-group>
				<view>
					<navigator :hover-stay-time="100">
						<view class="juzhong1">
							<uni-icons customPrefix="iconfont" type="icon-shouye" size="20"></uni-icons>
							<text class="zi1">我的活动</text>
						</view>
					</navigator>
				</view>
			</uni-group>
			<uni-group>
				<view>
					<navigator :hover-stay-time="100">
						<view class="juzhong1">
							<uni-icons customPrefix="iconfont" type="icon-tuijian" size="20"></uni-icons>
							<text class="zi1">推荐给好友</text>
						</view>
					</navigator>
					<hr>
					<navigator :hover-stay-time="100">
						<view class="juzhong1">
							<uni-icons customPrefix="iconfont" type="icon-shezhi" size="20"></uni-icons>
							<text class="zi1">设置</text>
						</view>
					</navigator>
				</view>
			</uni-group>
		</view>
	</view>
</template>

<script>
	 export default {
		methods:{
			saoma(){
				uni.scanCode({
				    onlyFromCamera: true,
				    success: function (res) {
				        console.log('条码类型：' + res.scanType);
				        console.log('条码内容：' + res.result);
				    }
				});
			}
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
	@import url("/static/person-icon/pericon.css");
	
	.juzhong{
		display: flex;
		margin: 10px;
		flex-direction: column;
		align-items: center;
	}
	.zi{
		font-size: 14px;
		margin-top: 5px;
		color: #7A7E83;
	}
	.juzhong1{
		height: 35px;
		display: flex;
		flex-direction: row;
		align-items: center;
		margin: 2px;
		
		/* padding-left: 10px; */
	}
	
	view>hr{
		background-color: #007AFF;
	}
	.zi1{
		margin-left: 10px;
		color: #7A7E83;
	}
</style>
