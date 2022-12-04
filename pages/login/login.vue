<template>
	<view>
		<!-- 样式图片 -->
		<image src="../../static/img/logo-1.png" class="logo" mode="widthFix"></image>
		<!--mode="widthFix" 代表是成比例的缩放 -->
		
		<!-- 主标题 -->
		<view class="logo-title">EMOS企业在线办公系统</view>
		
		<!-- 副标题 -->
		<view class="logo-subtitle">Vue 2022.11</view>
		
		<!-- 添加按钮获取信息 -->
		<button class="login-btn" open-type="getUserInfo" @tap="login()">登录系统</button>
		<!-- open-type="getUserInfo" 获取信息的属性，必须写 -->
		
		<!-- 链接文字 -->
		<view class="register-container">
			没有账号？
			<!-- 设置注册按钮 -->
			<text class="register" @tap="toRegister()">立即注册</text>
			<!-- 链接到注册页面 -->
			
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
			toRegister:function(){
				uni.navigateTo({
					url:"../register/register"
				})
			}
		}
	}
</script>

<style lang="less">
	@import url("login.less");
</style>
