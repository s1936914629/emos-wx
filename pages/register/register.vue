<template>
	<view>
		<!-- 设置图片 -->
		<image src="../../static/img/logo-2.png" mode="widthFix" class="logo"></image>
		
		<!-- 登录需要的容器 -->
		<view class="register-container">
			<!-- 邀请码文本框 -->
			<input type="text" placeholder="输入你的邀请码" class="register-code" maxlength="6" v-model="registerCode" />
			<!-- 描述文字 -->
			<view class="register-desc">管理员创建员工账号之后，你可以从你的个人邮箱中获得注册邀请码</view>
			<!-- 信息提取按钮 -->
			<button class="register-btn" open-type="getUserInfo" @tap="register()">执行注册</button>
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
			register:function(){
				uni.login({
					provider:"weixin",
					success:function(resp){
						// console.log(resp.code)
						let code = resp.code //获取临时授权
						
						//获取微信账号的基本信息
						uni.getUserInfo({
							provider:"weixin",
							success:function(resp){
								let nickName = resp.userInfo.nickName  //获取微信昵称
								let avatarUrl = resp.userInfo.avatarUrl //获取微信头像地址
								console.log(nickName)
								console.log(avatarUrl)
								
							}
						})
					}
				})
			}
		}
	}
</script>

<style lang="less">
	@import url('register.less');
</style>
