<template>
  <div class="dashboard-editor-container">
    <!--<github-corner></github-corner>-->


    <el-row :gutter="20" >
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="user1" />
            <span>用户名片</span>
          </div>
          <div class="component-item">
            <ul class="user-info">
            <li>用户名称</li>
            <li>邮箱</li>
            <li>电话号码</li>
            <li>职位</li>
            <li>项目组</li>
            </ul>
            <div class="see-more"><el-button  type="info" @click="">更多</el-button></div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="update" />
            <span>A3 SDK更新版本发布</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more"><el-button  type="info" @click="">更多</el-button></div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="buding" />
            <span>A2 SDK补丁</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more"><el-button  type="info" @click="">更多</el-button></div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="document" />
            <span>A3开发者文档</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more"><el-button  type="info" @click="">更多</el-button></div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="question" />
            <span>A3开发问题</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more"><el-button  type="info" @click="">更多</el-button></div>
          </div>
        </el-card>
      </el-col>

      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <svg-icon icon-class="push" />
            <span>A3测试工具发布</span>
          </div>
          <div class="component-item">
            SDK版本更新包含Android dev,ios dev,server等... 融云SDK 版本更新( Android 2.8.26 Stable;iOS 2.8.26 Stable) 22日 12月 融云SDK 版本更新
            <div class="see-more"><el-button  type="info" @click="">更多</el-button></div>
          </div>
        </el-card>
      </el-col>
    </el-row>

  </div>
</template>

<script>

</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.dashboard-editor-container {
  padding: 32px;
  background-color: rgb(240, 242, 245);
  .chart-wrapper {
    background: #fff;
    padding: 16px 16px 0;
    margin-bottom: 32px;
  }
}
</style>
