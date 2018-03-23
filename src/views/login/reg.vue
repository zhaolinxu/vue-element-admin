<template>
	<div class="reg-container">
		<img class="reg_logo" :src="RegLogo" alt="全志一号通">

		<el-form class="reg-form" autoComplete="on" label-position="left">
			<div class="form-content">
				<div class="title-container">
					<h3 class="title">欢迎注册全志客户服务</h3>
				</div>
				<el-form-item>
					<el-tooltip popper-class="tooltip-reg" effect="light" content="请输入会员名称" placement="right-start" >
					<el-input type="text" autoComplete="on" placeholder="会员名" />
					</el-tooltip>
				</el-form-item>
				<el-select v-model="value" placeholder="国家">
					<el-option v-for="item in options" :key="item.value" :label="item.label" :value="item.value">
					</el-option>
				</el-select>
				<el-form-item>
					<el-tooltip popper-class="tooltip-reg" effect="light" content="请输入公司全称" placement="right-start" >
					<el-input type="text" autoComplete="on" placeholder="公司全称" />
					</el-tooltip>
				</el-form-item>
				<el-form-item>
					<el-tooltip popper-class="tooltip-reg" effect="light" content="密码需包含数字、字母、标点符号(如. / _等,除空格外)中的三种，8-20个字符" placement="right-start" >
						<el-input :type="passwordType" autoComplete="on" placeholder="密码" />
					</el-tooltip>
				</el-form-item>
				<el-form-item>
					<el-tooltip popper-class="tooltip-reg" effect="light" content="请重复输入密码" placement="right-start" >
					<el-input :type="passwordType" autoComplete="on" placeholder="确认密码" />
					</el-tooltip>
				</el-form-item>
				<el-form-item>
					<el-tooltip popper-class="tooltip-reg" effect="light" content="请输入你的邮箱" placement="right-start" >
					<el-input type="text" autoComplete="on" placeholder="邮箱" />
					</el-tooltip>
				</el-form-item>
				<el-checkbox v-model="checked">随时邮件了解全志产品动态，最新资讯</el-checkbox>
				<el-button type="primary" class="btn-reg" :loading="loading" @click.native.prevent="handleLogin">重建账号</el-button>

			</div>
		</el-form>
		<div class="go-login">
			<span class="tips-reg">已有账号？</span>
			<el-button type="text">立即登录</el-button>
		</div>
		<div class="copyright">
			<div class="copy-container">
				<div class="company-gray">Copyright © www.allwinner service.com, All Rights Reserved.珠海全志科技股份有限公司
				</div>
				<lang-select class="set-language"></lang-select>
			</div>
		</div>

	</div>
</template>

<script>
	import { isvalidUsername } from '@/utils/validate'
	import LangSelect from '@/components/LangSelect'
	import SocialSign from './socialsignin'
	import RegLogo from '@/assets/logo_blue.png'

	export default {
		components: { LangSelect, SocialSign },
		name: 'login',
		data() {

			return {
				passwordType: 'password',
				loading: false,
				showDialog: false,
				RegLogo,
				options: [{
					value: '选项1',
					label: '黄金糕'
				}, {
					value: '选项2',
					label: '双皮奶'
				}, {
					value: '选项3',
					label: '蚵仔煎'
				}, {
					value: '选项4',
					label: '龙须面'
				}, {
					value: '选项5',
					label: '北京烤鸭'
				}],
				value: ''
			}
		},
		methods: {
			showPwd() {
				if(this.passwordType === 'password') {
					this.passwordType = ''
				} else {
					this.passwordType = 'password'
				}
			},
			handleLogin() {
				this.$refs.loginForm.validate(valid => {
					if(valid) {
						this.loading = true
						this.$store.dispatch('LoginByUsername', this.loginForm).then(() => {
							this.loading = false
							this.$router.push({ path: '/' })
						}).catch(() => {
							this.loading = false
						})
					} else {
						console.log('error submit!!')
						return false
					}
				})
			},
			afterQRScan() {
				// const hash = window.location.hash.slice(1)
				// const hashObj = getQueryObject(hash)
				// const originUrl = window.location.origin
				// history.replaceState({}, '', originUrl)
				// const codeMap = {
				//   wechat: 'code',
				//   tencent: 'code'
				// }
				// const codeName = hashObj[codeMap[this.auth_type]]
				// if (!codeName) {
				//   alert('第三方登录失败')
				// } else {
				//   this.$store.dispatch('LoginByThirdparty', codeName).then(() => {
				//     this.$router.push({ path: '/' })
				//   })
				// }
			}
		},
		created() {
			// window.addEventListener('hashchange', this.afterQRScan)
		},
		destroyed() {
			// window.removeEventListener('hashchange', this.afterQRScan)
		},
		goReg() {
			this.$router.push({ path: '/' })
		}
	}
</script>