<template>
	<view class="about-page">
		<view class="header">
			<image class="logo" src="your-logo.png" mode="aspectFit"></image>
			<text class="app-name">你的App名称</text>
		</view>
		<view class="content">
			<view class="section">
				<text class="section-title">关于我们</text>
				<text class="section-description">我们是最棒的.</text>
			</view>
			<view class="section">
				<text class="section-title">我们的项目</text>
				<text class="section-description">非常不错.</text>
			</view>
			<view class="section">
				<text class="section-title">联系我们</text><br>
				<text class="section-description">邮箱: 12345@123.com</text><br>
				<text class="section-description">电话: +123 456 7890</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style scoped>
	.about-page {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 20px;
	}

	.header {
		display: flex;
		align-items: center;
		margin-bottom: 20px;
	}

	.logo {
		width: 80px;
		height: 80px;
		margin-right: 10px;
	}

	.app-name {
		font-size: 24px;
		font-weight: bold;
	}

	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.section {
		margin-bottom: 20px;
	}

	.section-title {
		font-size: 20px;
		font-weight: bold;
		margin-bottom: 10px;
	}

	.section-description {
		font-size: 16px;
	}
</style>