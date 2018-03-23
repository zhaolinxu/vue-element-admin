<template>
	<div class="login-container" :style="bg">
		<div class="login-left">
			<img class="login-logo" :src="LoginLogo" alt="全志一号通">
			<h3><div></div>全志开发服务平台</h3>
			<ul>
				<li>企业认证、填写资料、上传资料</li>
				<li>产品认证</li>
				<li>文档、资料、开发工具下载，并提供技术支持</li>
			</ul>
		</div>
		<el-form class="login-form" autoComplete="on" :model="loginForm" :rules="loginRules" ref="loginForm" label-position="left">
			<div class="title-container">
				<h3 class="title">{{$t('login.title')}}</h3>
			</div>
			<el-form-item prop="username">
				<el-input name="username" type="text" v-model="loginForm.username" autoComplete="on" placeholder="用户名" />
			</el-form-item>

			<el-form-item prop="password">
				<el-input name="password" :type="passwordType" @keyup.enter.native="handleLogin" v-model="loginForm.password" autoComplete="on" placeholder="登录密码" />
			</el-form-item>

			<el-button type="primary" class="btn-login" :loading="loading" @click.native.prevent="handleLogin">{{$t('login.logIn')}}</el-button>

			<div class="go-reg">
				<span class="tips-reg">还没有注册一号通账号？</span>
				<el-button plain>立即注册</el-button>
			</div>
		</el-form>
		<div class="copyright">
			<div class="copy-container">
				<div class="company">Copyright © www.allwinner service.com, All Rights Reserved.珠海全志科技股份有限公司
				</div>
				<lang-select class="set-language"></lang-select>
			</div>
		</div>

		<el-dialog :title="$t('login.thirdparty')" :visible.sync="showDialog" append-to-body>
			{{$t('login.thirdpartyTips')}}
			<br/>
			<br/>
			<br/>
			<social-sign />
		</el-dialog>

	</div>
</template>

<script>
	import { isvalidUsername } from '@/utils/validate'
	import LangSelect from '@/components/LangSelect'
	import SocialSign from './socialsignin'
	import LoginLogo from '@/assets/logo.png'

	export default {
		components: { LangSelect, SocialSign },
		name: 'login',
		data() {
			const validateUsername = (rule, value, callback) => {
				if(!isvalidUsername(value)) {
					callback(new Error('请输入用户名'))
				} else {
					callback()
				}
			}
			const validatePassword = (rule, value, callback) => {
				if(value.length < 6) {
					callback(new Error('The password can not be less than 6 digits'))
				} else {
					callback()
				}
			}
			return {
				bg: {
					backgroundImage: "url(" + require("../../assets/images/login/bg.jpg") + ")",
					backgroundRepeat: "no-repeat",
					backgroundSize: "cover",
				},
				loginForm: {
					username: 'admin',
					password: '1111111'
				},
				loginRules: {
					username: [{ required: true, trigger: 'blur', validator: validateUsername }],
					password: [{ required: true, trigger: 'blur', validator: validatePassword }]
				},
				passwordType: 'password',
				loading: false,
				showDialog: false,
				LoginLogo
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
		},goReg(){
			this.$router.push({ path: '/' })
		}
	}
</script>