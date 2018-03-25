<template>
	<div class='sdk-container mainbody'>
		<h3>SDK发布申请单 流水号2016062334521</h3>
		<el-form class="skd-form" label-width="150px">
			<div class="form-title">申请人信息</div>
			<el-row :gutter="20">
				<el-col :span="8">
					<el-form-item label="申请人：">
						王五
					</el-form-item>
					<el-form-item label="申请时间：">
						2018-02-01
					</el-form-item>
					<el-form-item label="申请类型：">
						<el-select placeholder="版本发布">
							<el-option label="补丁发布" value=""></el-option>
							<el-option label="demo版本" value=""></el-option>
						</el-select>
					</el-form-item>
				</el-col>
				<el-col :span="8">
					<el-form-item label="地区：">
						珠海
					</el-form-item>
					<el-form-item label="申请人部门：">
						BU2－运营部－PD
					</el-form-item>
					<el-form-item label="发布类型：">
						<el-select placeholder="版本发布">
							<el-option label="升级" value=""></el-option>
							<el-option label="全部发布" value=""></el-option>
						</el-select>
					</el-form-item>

				</el-col>
				<el-col :span="8">
					<el-form-item label="申请类型：">
						自助申请角色
					</el-form-item>
					<el-form-item label="申请人部门详情：">
						蚂蚁金融云－体验技术产品－2组
					</el-form-item>

				</el-col>
			</el-row>
			<div class="form-title">项目信息</div>
			<el-row :gutter="20">
				<el-col :span="8">
					<el-form-item label="项目：">
						<el-select placeholder="H 1 标案">
							<el-option label="补丁发布" value=""></el-option>
							<el-option label="demo版本" value=""></el-option>
						</el-select>
					</el-form-item>
				</el-col>
			</el-row>
			<el-row :gutter="20">
				<el-col :span="8">
					<el-form-item label="技术经理：" required>
						<el-input placeholder="xxx"></el-input>
					</el-form-item>
				</el-col>
				<el-col :span="8">
					<el-form-item label="QA：" required>
						<el-input placeholder="xxx"></el-input>
					</el-form-item>
				</el-col>
				<el-col :span="8">
					<el-form-item label="代码验证师：" required>
						<el-input placeholder="xxx"></el-input>
					</el-form-item>
				</el-col>
			</el-row>
			<div class="form-title no-pb">客户信息</div>
			<el-row :gutter="20">
				<el-col :span="24" class="align-right">
					<el-button type="primary" icon="el-icon-plus">添加</el-button>
				</el-col>
			</el-row>
			<el-table :data="userData" class="tb-customer">
				<el-table-column prop="name" label="客户" width="180">
				</el-table-column>
				<el-table-column prop="email" label="对方账号" width="180">
				</el-table-column>
				<el-table-column prop="creattime" label="邮箱">
				</el-table-column>
				<el-table-column prop="email" label="NDA" width="180">
				</el-table-column>
				<el-table-column prop="email" label="NDA范围" width="180">
				</el-table-column>
				<el-table-column label="操作">
					<template slot-scope="scope">
						<el-button type="text" size="small">删除</el-button>
						<el-button type="text" size="small">编辑</el-button>
					</template>
				</el-table-column>
			</el-table>

			<div class="form-title">版本信息</div>
			<el-row :gutter="20">
				<el-col :span="6">
					<el-form-item label="repo库名：">
						<el-input placeholder="请输入xxx"></el-input>
					</el-form-item>
				</el-col>
				<el-col :span="6">
					<el-form-item label="内部服务器地址：">
						<el-input placeholder="请输入xxx"></el-input>
					</el-form-item>
				</el-col>
				<el-col :span="6">
					<el-form-item label="内部tag：">
						<el-input placeholder="请输入xxx"></el-input>
					</el-form-item>
				</el-col>
				<el-col :span="6">
					<el-form-item label="已发布tag：">
						<el-input placeholder="请输入xxx"></el-input>
					</el-form-item>
				</el-col>
			</el-row>
			<el-row :gutter="20">
				<el-col :span="12">
					<el-form-item label="对外分支：">
						<el-input placeholder="请输入xxx"></el-input>
					</el-form-item>
				</el-col>
				<el-col :span="12">
					<el-form-item label="名称：">
						<el-input placeholder="请输入xxx"></el-input>
					</el-form-item>
				</el-col>
			</el-row>
			<el-row :gutter="20">
				<el-col :span="12">
					<el-form-item label="TR5评审附件：">
						<el-upload class="upload-demo" action="https://jsonplaceholder.typicode.com/posts/" :on-change="handleChange" :file-list="fileList3">
							<el-button size="small" type="primary">上传文件</el-button>
							<div slot="tip" class="el-upload__tip">支持扩展名：.rar .zip .doc .docx .pdf .jpg.</div>
						</el-upload>
					</el-form-item>
				</el-col>

			</el-row>
			<el-form-item class="btn-group">
				<el-button type="primary">提交</el-button>
				<el-button>保存</el-button>
				<el-button>取消</el-button>
			</el-form-item>
		</el-form>
	</div>
</template>

<script>
	import Chart from '@/components/Charts/keyboard'

	export default {
		name: 'keyboardChart',
		data() {
			return {
				userData: [{
					creattime: '2016-05-02',
					name: '王小虎',
					email: '123456@qq.com'
				}, {
					creattime: '2016-05-02',
					name: '王小虎',
					email: '123456@qq.com'
				}, {
					creattime: '2016-05-02',
					name: '王小虎',
					email: '123456@qq.com'
				}, {
					creattime: '2016-05-02',
					name: '王小虎',
					email: '123456@qq.com'
				}, {
					creattime: '2016-05-02',
					name: '王小虎',
					email: '123456@qq.com'
				}]
			}
		},
		components: {}
	}
</script>

<style scoped>
	.chart-container {
		position: relative;
		padding: 20px;
		width: 100%;
		height: 85vh;
	}
</style>