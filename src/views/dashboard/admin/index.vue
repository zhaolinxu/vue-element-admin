<template>
	<div class="dashboard-editor-container">
		<!--<github-corner></github-corner>-->

		<el-row :gutter="20">
			<el-col :span="8">
				<el-card class="box-card">
					<div slot="header" class="clearfix">
						<span>待办事项</span>
						<el-badge :value="5" :max="99" class="item"></el-badge>
					</div>
					<div class="component-item">
						<ul class="tipsList">
							<li class="unread">
								<div class="circle circle-blue ">流程
								</div>
								<div class="right">
									<div>审批流程已退回，请修改20145874资料</div>
									<span>2018-02-28 17:00:00</span>
								</div>
							</li>
							<li class="unread">
								<div class="circle circle-green ">反馈
								</div>
								<div class="right">
									<div>您的反馈有新的回复，请查看！</div>
									<span>2018-02-28 17:00:00</span>
								</div>
							</li>
						</ul>

					</div>
					<div class="see-more">
						<el-button type="text">查看更多</el-button>
					</div>
				</el-card>
			</el-col>

			<el-col :span="8">
				<el-card class="box-card">
					<template>
						<el-tabs v-model="activeName2" @tab-click="handleClick">
							<el-tab-pane label="未处理" name="first">
								<ul class="tipsList">
									<li>
										<div class="circle circle-blue ">问题
										</div>
										<div class="right">
											<div>审批流程已退回，请修改20145874资料</div>
											<span>2018-02-28 17:00:00</span>
										</div>
									</li>
									<li class="unread">
										<div class="circle circle-yellow ">问题
										</div>
										<div class="right">
											<div>这是一段文字内容这是一段文字内容哟有时候内容会超出长度这是一段文字内容这是一段文字内容哟有时候内容会超出长度</div>
											<span>2018-02-28 17:00:00</span>
										</div>
									</li>
								</ul>
							</el-tab-pane>
							<el-tab-pane label="处理中" name="second">222</el-tab-pane>
							<el-tab-pane label="已处理" name="third">333</el-tab-pane>
						</el-tabs>
					</template>
					<div class="see-more">
						<el-button type="text">查看更多</el-button>
					</div>
				</el-card>
			</el-col>
			<el-col :span="8">
				<el-card class="box-card">
					<div slot="header" class="clearfix">
						<span>服务消息</span>
						<el-badge :value="25" :max="99" class="tit-badge"></el-badge>
					</div>
					<div class="component-item">
						<ul class="tipsList">
							<li>
								<div class="circle circle-blue ">问题
								</div>
								<div class="right">
									<div>审批流程已退回，请修改20145874资料</div>
									<span>2018-02-28 17:00:00</span>
								</div>
							</li>
							<li class="unread">
								<div class="circle circle-yellow ">问题
								</div>
								<div class="right">
									<div>这是一段文字内容这是一段文字内容哟有时候内容会超出长度这是一段文字内容这是一段文字内容哟有时候内容会超出长度</div>
									<span>2018-02-28 17:00:00</span>
								</div>
							</li>
						</ul>
					</div>

					<div class="see-more">
						<el-button type="text">查看更多</el-button>
					</div>
				</el-card>
			</el-col>
		</el-row>
		<el-row :gutter="20">
			<el-col :span="16">
				<el-carousel trigger="click" class="imgSlide" height="220px">
					<el-carousel-item v-for="item in 4" :key="item">
						<img :src="slideImg" alt="全志一号通">
					</el-carousel-item>
				</el-carousel>

				<div>
					<el-card class="box-card">
						<template>
							<el-tabs v-model="activeName" @tab-click="handleClick" class="tab-product">
								<el-tab-pane label="产品需求" name="first">
									<el-form :inline="true" :model="formInline" class="form-xuqiu">
										<el-row :gutter="20">
											<el-col :span="12">
												<el-form-item label="平台：" :span="12">
													<el-select v-model="formInline.system" placeholder="请选择">
														<el-option label="类型一" value="0"></el-option>
														<el-option label="类型二" value="1"></el-option>
													</el-select>
												</el-form-item>
											</el-col>
											<el-col :span="12">
												<el-form-item label="类型：" :span="12">
													<el-select v-model="formInline.type" placeholder="请选择">
														<el-option label="类型一" value="0"></el-option>
														<el-option label="类型二" value="1"></el-option>
													</el-select>
												</el-form-item>
											</el-col>
											<el-col>
												<el-form-item label="需求：">
													<el-input type="textarea" v-model="formInline.desc"></el-input>
												</el-form-item>
											</el-col>
										</el-row>

										<div class="see-more">
											<el-button plain class="btn-sub">提交</el-button>
										</div>
									</el-form>
								</el-tab-pane>
								<el-tab-pane label="质量投诉" name="second">
									222
								</el-tab-pane>
								<el-tab-pane label="体验建议" name="third">
									3333
								</el-tab-pane>
								<el-tab-pane label="其它反馈" name="fourth">
									444
								</el-tab-pane>
							</el-tabs>
						</template>
					</el-card>

				</div>
			</el-col>
			<el-col :span="8">
				<el-card class="box-card">
					<div slot="header" class="clearfix">
						<span>新品发布</span>
					</div>
					<div class="component-item">
						<img class="img-newProduct" :src="newProduct" />
						<div class="newDec">SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新</div>
						<div class="see-more">
							<el-button type="text">更多新品</el-button>
						</div>
					</div>
				</el-card>
				<el-card class="box-card card-resource">
					<div slot="header" class="clearfix">
						<span>我的资源</span>
					</div>
					<div class="component-item">
						<ul class="tipsList userProfile">
							<li>
								<div class="circle">
									<img :src="newProduct" />
								</div>
								<div class="right">
									<div>Mark Elliot Zuckerberg</div>
									<div class="tags">
										<span class="tag-rz"><b>V</b>企业认证</span>
										<span class="tag-lv">lv.69</span>
									</div>
								</div>
							</li>
						</ul>
						产品认证
						<ul class="productRz">
							<li>A63</li>
							<li>VR9</li>
							<li>A64</li>
						</ul>
					</div>

					<div class="see-more">
						<el-button type="text">查看更多</el-button>
					</div>
				</el-card>

			</el-col>
		</el-row>

	</div>
</template>
<!--<script :src="Jquery" type="text/javascript" charset="utf-8"></script>-->
<script>
//	import Jquery from '@/assets/js/jquery.min.js'
	import PieChart from './components/PieChart'
	import slideImg from '@/assets/images/workshop/demo_l.jpg'
	import newProduct from '@/assets/images/workshop/demo_r.jpg'
	export default {
		name: 'dashboard-admin',
		components: {
			PieChart
		},
		data() {
			return {
				activeName: 'first',
				activeName2: 'first',
				slideImg,
				newProduct,
				formInline: {
					system: '',
					type: '',
					desc: ''
				}
			};
		},
		methods: {
			handleClick(tab, event) {
				console.log(tab, event);
			}

		}
	}
	//	var imgHeight = $(".imgSlide img").height();
	//		console.log(imgHeight)
	//		$(".el-carousel__container").css("height",imgHeight);
</script>