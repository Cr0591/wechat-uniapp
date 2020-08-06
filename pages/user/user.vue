<template>
	<view class="user">
		<!-- 头部 -->
		<view class="user-wrap">
			<view class="setting iconfont icon31shezhi"></view>
			<view class="info">
				<image class="avatar" mode="aspectFill" :src="userInfo.headPicUrl"></image>
				<view class="nickname">{{ userInfo.nickName }}</view>
			</view>
		</view>


		<!-- 滑动导航 -->
		<view style="border-radius: 20rpx; overflow: hidden; margin: 0 20rpx;">
			<com-nav :list="list" :col="4"></com-nav>
		</view>

		<!-- 用户功能 -->
		<view class="com-item">
			<view class="com-wrap">
				<view class="cell" v-for="(item, index) in userList" :key="index">
					<view class="cell-left">
						<image class="cell-icon" :src="item.icon" mode="aspectFill"></image>
						<view class="cell-text">{{ item.title }}</view>
					</view>
					<view class="iconfont iconmore1"></view>
				</view>
			</view>
		</view>

		<!-- 用户服务 -->
		<view class="com-item">
			<view class="com-wrap">
				<view class="cell" v-for="(item, index) in serverList" :key="index">
					<view class="cell-left">
						<image class="cell-icon" :src="item.icon" mode="aspectFill"></image>
						<view class="cell-text">{{ item.title }}</view>
					</view>
					<view class="iconfont iconmore1"></view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
import comNav from './components/com-nav.vue'
export default {
	components: {
		comNav
	},
	data() {
		return {
			userInfo: {
				headPicUrl: '/static/images/user/avatar.jpg',
				nickName: '史蒂芬.林'
			},
			currentIndex: 0,
			list: [
				
				{
					icon: '/static/images/user/class-01.png',
					text: '我发布的'
				},
				{
					icon: '/static/images/user/class-02.png',
					text: '我帮助的'
				},
				{
					icon: '/static/images/user/class-03.png',
					text: '提现'
				},
				{
					icon: '/static/images/user/class-04.png',
					text: '申请接单'
				}
			],
			userList: [
				{
					title: '我的信息',
					icon: '/static/images/user/icon-collect.png',
					path: 'address-list'
				},
				{
					title: '收货地址',
					icon: '/static/images/user/icon-address.png',
					path: 'address-list'
				},
				
				{
					title: '我的足迹',
					icon: '/static/images/user/icon-foot.png',
					path: 'browse-list'
				}
			],
			serverList: [
				{
					title: '客服中心',
					icon: '/static/images/user/icon-kefu.png',
					path: 'kefu'
				},
				{
					title: '帮助中心',
					icon: '/static/images/user/icon-help.png',
					path: 'help'
				},
				{
					title: '版本',
					icon: '/static/images/user/icon-about.png',
					text: '1.0.0'
				}
			]
		};
	}
};
</script>

<style lang="scss">
page {
	background: #f2f2f2;
}
.btn-hover {
	background: #f2f2f2 !important;
}
.user {
	.user-wrap {
		display: flex;
		justify-content: center;
		align-items: center;
		height: 30vw;
		padding: 30rpx;
		z-index: 9;
		border-radius: 0 0 20% 20%;
		background: url('https://handsel.oss-cn-shenzhen.aliyuncs.com/1588938371592.jpg') no-repeat;
		background-size: cover;
		.setting {
			color: #fff;
			position: absolute;
			top: 60rpx;
			left: 60rpx;
			font-size: 50rpx;
		}
		.info {
			position: absolute;
			text-align: center;
			.avatar {
				width: 150rpx;
				height: 150rpx;
				border-radius: 50%;
			}
			.nickname {
				color: #fff;
				font-size: 28rpx;
			}
		}
	}
	.com-item {
		padding-left: 20rpx;
		padding-right: 20rpx;
		margin-top: 20rpx;
		.com-wrap {
			border-radius: 25rpx;
			overflow: hidden;
		}
	}
	.cell {
		height: 80rpx;
		padding-left: 20rpx;
		padding-right: 20rpx;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background: #fff;
		border-bottom: 1px solid #f8f8f8;
		&:active {
			background: #f2f2f2;
		}
		&:last-child {
			border-bottom: none !important;
		}
		.cell-left {
			display: flex;
			align-items: center;
			.cell-icon {
				width: 50rpx;
				height: 50rpx;
			}
			.cell-text {
				color: #666;
				font-size: 28rpx;
				margin-left: 20rpx;
			}
		}
		.iconfont {
			font-size: 40rpx;
			color: #999;
		}
	}
}
</style>
