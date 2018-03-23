<template>
	<div class="userlist-container">

		<el-row :gutter="20">
			<el-col :span="6">
				<h3>UI设计-文档列表</h3>
			</el-col>
			<el-col :span="12" :offset="6" class="align-right">
				<el-button type="primary" icon="el-icon-plus">下载</el-button>
			</el-col>
		</el-row>
		<el-table :data="userData" style="width: 100%">
			<el-table-column type="selection" width="55">
			</el-table-column>
			<el-table-column prop="name" label="文件名">
			</el-table-column>
			<el-table-column prop="dec" label="描述">
			</el-table-column>
			<el-table-column prop="number" label="NO.">
			</el-table-column>
			<el-table-column prop="verson" label="版本">
			</el-table-column>
			<el-table-column width="100px" label="评分">
				<el-rate v-model="value1"></el-rate>
			</el-table-column>
			<el-table-column prop="time" label="时间">
			</el-table-column>

		</el-table>
	</div>
</template>

<script>
	import { fetchList } from '@/api/article'
	export default {
		data() {
			return {
				userData: [{
					name: 'xx设计文档',
					dec: '123456@qq.com',
					number: 'VR9-1.01',
					verson: '1.01',
					rate: '5',
					time: '2018-03-22 12:13:14',
				}, {
					name: 'xx设计文档',
					dec: '123456@qq.com',
					number: 'VR9-1.01',
					verson: '1.01',
					rate: '5',
					time: '2018-03-22 12:13:14',
				}, {
					name: 'xx设计文档',
					dec: '123456@qq.com',
					number: 'VR9-1.01',
					verson: '1.01',
					rate: '5',
					time: '2018-03-22 12:13:14',
				}]
			}
		}
	}
</script>