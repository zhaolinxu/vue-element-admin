<template>
  <div class="dashboard-editor-container">
    <!--<github-corner></github-corner>-->


    <el-row :gutter="15">
      <el-col :span="8">
        <el-card class="box-card user-info">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="user1"/>
            <span>用户名片</span>
          </div>
          <div class="component-item">
            <ul>
              <li>用户名称：admin</li>
              <li>邮箱：admin@163.com</li>
              <li>电话号码：18684061245</li>
              <li>职位：经理</li>
              <li>项目组：xxxx</li>
            </ul>
            <svg-icon icon-class="working" class="workman" />
            <div class="see-more">
              <el-button type="info" @click="">更多</el-button>
            </div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-row :gutter="15">
          <el-col :span="12">
            <el-card class="box-card">
              <div slot="header" class="clearfix">
                <span>A3-6619项目(8)</span>
              </div>
              <div class="component-item">
                <ul>
                  <li>项目1</li>
                  <li>项目2</li>
                  <li>项目3</li>
                  <li>...</li>
                </ul>

              </div>
            </el-card>
          </el-col>
          <el-col :span="12">
            <el-card class="box-card">
              <div slot="header" class="clearfix">
                <span>A3-2201项目(9)</span>
              </div>
              <div class="component-item">
                <ul>
                  <li>项目1</li>
                  <li>项目2</li>
                  <li>项目3</li>
                  <li>...</li>
                </ul>

              </div>
            </el-card>
          </el-col>
        </el-row>
        <el-row :gutter="15">
          <el-col :span="12">
            <el-card class="box-card">
              <div slot="header" class="clearfix">
                <span>提交问题</span>
              </div>
              <div class="component-item">
                <div class="number">22</div>

              </div>
            </el-card>
          </el-col>
          <el-col :span="12">
            <el-card class="box-card">
              <div slot="header" class="clearfix">
                <span>关闭问题</span>
              </div>
              <div class="component-item">
                <div class="number">18</div>

              </div>
            </el-card>
          </el-col>
        </el-row>

      </el-col>

      <el-col :span="8">
        <el-row :gutter="15">
          <el-col :span="12">
            <el-card class="box-card">
              <div slot="header" class="clearfix">
                <span>A3-6619项目(8)</span>
              </div>
              <div class="component-item">
                <ul>
                  <li>项目1</li>
                  <li>项目2</li>
                  <li>项目3</li>
                  <li>...</li>
                </ul>
              </div>
            </el-card>
          </el-col>
          <el-col :span="12">
            <el-card class="box-card">
              <div slot="header" class="clearfix">
                <span>SDk/补丁</span>
              </div>
              <div class="component-item">
                <div class="number">2/27</div>

              </div>
            </el-card>
          </el-col>
        </el-row>
        <el-row :gutter="15">
          <el-col :span="12">
            <el-card class="box-card chart">
              <div slot="header" class="clearfix">
                <span>活跃比例</span>
              </div>
              <div class="component-item">
                <!--<div class="chart-wrapper">-->
                  <!--<pie-chart></pie-chart>-->
                <!--</div>-->

              </div>
            </el-card>
          </el-col>
          <el-col :span="12">
            <el-card class="box-card">
              <div slot="header" class="clearfix">
                <span>文档统计</span>
              </div>
              <div class="component-item">
                <div class="number">13/97</div>

              </div>
            </el-card>
          </el-col>
        </el-row>

      </el-col>
    </el-row>
    <el-row :gutter="15" class="box-bottom">

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="document"/>
            <span>A3开发者文档</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more">
              <el-button type="info" @click="">更多</el-button>
            </div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="question"/>
            <span>A3开发问题</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more">
              <el-button type="info" @click="">更多</el-button>
            </div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="push"/>
            <span>A3测试工具发布</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more">
              <el-button type="info" @click="">更多</el-button>
            </div>
          </div>
        </el-card>
      </el-col>
    </el-row>

  </div>
</template>

<script>
  import PieChart from './components/PieChart'
  export default {
    name: 'dashboard-admin',
    components: {
      PieChart
    }
  }
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
  .dashboard-editor-container {
    padding: 20px;
    background-color: rgb(240, 242, 245);
    .chart-wrapper {
      background: #fff;
      padding: 16px 16px 0;
      margin-bottom: 32px;
    }

  }
</style>
