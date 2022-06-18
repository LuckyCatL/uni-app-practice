<template>
	<view>
		<view style="background-color: #FFFFFF;">
			<form>
				<textarea placeholder="说点什么吧! (≧∇≦)ﾉ" :show-confirm-bar="false" @input="sum" class="shuru"></textarea>
				<text style="color:#7D8B8D; margin-left: 300px;">{{fontsum}}/140</text>
				<uni-file-picker limit="5" style="margin-left: 20px;" mode="grid"></uni-file-picker>
				<br>
				<view class="butt">
					<view style="width:210;margin-left: 20px;">
						<checkbox>我已阅读并同意以上规范</checkbox>
					</view>
					<button class="butto">
							<text style="color: #FFFFFF;">发布</text>
					</button>
				</view>
			</form>
		</view>
		<br>
		<view class="bottom">
			<view style="width: 300px;margin-left: 20px;">
				<text>
					请大家遵循以下规范：
					1,
					2,
					3,
				</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"shangchuan",
		data(){
			return{
				fontsum:0,
			}
		},
		methods:{
			sum(e){
				// console.log(e)
				this.fontsum=e.detail.value.length;
			}
		}
	}
</script>

<style scoped>
	.shuru{
		/* background-image:url('/static/img/bck.png'); */
		/* background-size:100% 100% ; */
		background-color: #FFFFFF;
		height: 202.5px;
		width: 360px;
	}
	
	.butt{
		position: fixed;
		right: 0;
		bottom: calc( var(--window-bottom) + 3px);
		left: 0;
		z-index: 1030;
		margin-bottom: 10px;
		background-color: rgba( 186, 218, 85, 0);
		height: 40px;
		display: flex;
		justify-content: space-around;
		align-items: center;
	}
	.butto{
		width: 100px;
		background-color: #007AFF;
		border-radius: 30px;
	}
	
	.bottom{
		width: 360px;
		
		background-color: #FFFFFF;
	}
</style>
