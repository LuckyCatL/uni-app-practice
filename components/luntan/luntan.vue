<template>
	<view>
		<view>
			<uni-card title="这是一个ID" thumbnail="/static/img/1.png" is-shadow="true">
				<text>这是一条评论。。。。。。</text>
				<image  style="width: 100%;" src="/static/img/1.png" ></image>
				<view slot="actions" class="card-actions">
					<view class="card-actions-item" @click="open()">
						<uni-icons type="redo" size="22" color="#999"></uni-icons>
						<text class="card-actions-item-text">分享</text>
					</view>
					<view class="card-actions-item" @click="dianzan2()">
						<uni-icons :type="aaa" size="22" :color="col"></uni-icons>
						<text class="card-actions-item-text">点赞</text>
					</view>
					<view class="card-actions-item" @click="">
						<uni-icons type="chatbubble" size="22" color="#999"></uni-icons>
						<text class="card-actions-item-text">评论</text>
					</view>
				</view>
			</uni-card>
		</view>
		
		<view>
			<uni-popup ref="popup" type="share" :safeArea="false">
				<uni-popup-share title="分享到" @select="select"></uni-popup-share>
			</uni-popup>
		</view>
	</view>
</template>

<script>
	export default {
		name:"luntan",
		data(){
			return{
				color:"#000000",
				dianzan:0,
				aaa:"heart",
				col:"#999"
			}
		},
		methods:{
			open(){
			        this.$refs.popup.open('bottom')
				},
			dianzan2(){
				if(this.dianzan==0){
					this.aaa="heart-filled"
					this.dianzan = 1
					this.col="red"
				}else{
					this.aaa="heart"
					this.dianzan=0
					this.col="#999"
				}
			}
		}
	}
</script>

<style scoped>
	.card-actions{
		display: flex;
		height: 30px;
		justify-content: space-around;
		flex-direction:row;
		align-items: center;
	}
	
	.card-actions-item{
		/* display: flex; */
		/* width: 50px; */
	}
	
	.card-actions-item-text{
		font-size: 18px;
	}
</style>
