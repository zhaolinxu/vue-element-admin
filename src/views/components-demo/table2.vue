<template>
	<div class="userlist-container">
		<el-breadcrumb separator="/">
			<el-breadcrumb-item>工作台</el-breadcrumb-item>
			<el-breadcrumb-item>用户管理</el-breadcrumb-item>
			<el-breadcrumb-item>用户详情</el-breadcrumb-item>
		</el-breadcrumb>

		<el-row :gutter="20">
			<el-col :span="6">
				<h3>用户列表</h3>
			</el-col>
			<el-col :span="12" :offset="6" class="align-right">
				<el-button type="primary" icon="el-icon-plus">新建用户</el-button>
			</el-col>
		</el-row>
		<el-table :data="userData" style="width: 100%">
			<el-table-column prop="name" label="姓名" width="180">
			</el-table-column>
			<el-table-column prop="email" label="邮箱" width="180">
			</el-table-column>
			<el-table-column prop="creattime" label="创建时间">
			</el-table-column>
			<el-table-column label="操作">
				<template slot-scope="scope">
					<el-button type="text" size="small">删除</el-button>
					<el-button type="text" size="small">编辑</el-button>
					<el-button type="text" size="small">加入组</el-button>
					<el-button type="text" size="small">发送邀请</el-button>
				</template>
			</el-table-column>
		</el-table>
	</div>
</template>

<script>
	export default {
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
		}
	}
</script>