<template>
	<view>
		<view class="touxiang">
			<image class="images" :src="src" @error="imageError"></image>
			<p></p>
			<text>良匠</text>
		</view>
		<view style="padding-top: 20rpx;">
			 <uni-list>
			    <uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="我的信息" @tap="toMyInfo" />
				<uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="我的地址" @click="toMyAddr"/>
				<uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="提现" @click="toWithdraw"/>
			</uni-list>
		</view>
		
		<view style="padding-top: 20rpx;">
			 <uni-list>
			    <uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="微信客服" />
				<uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="电话客服" />
				<uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="关于我们" />
			</uni-list>
		</view>
		<view style="padding-top: 20rpx;">
			 <uni-list>
			    <uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="申请接单" />
			</uni-list>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				src: 'https://vkceyugu.cdn.bspapp.com/VKCEYUGU-uni-app-doc/7c946930-bcf2-11ea-b997-9918a5dda011.png',
			}
		},
		methods: {
			toMyInfo(){
				console.log("wopcao")
				uni.navigateTo({
					url: './myinfo',
				});
			},
			toMyAddr(){
				uni.navigateTo({
					url: './myaddress'
				})
			},
			toWithdraw(){
				uni.navigateTo({
					url: './withdraw'
				})
			}
		}
	}
</script>

<style>

</style>
