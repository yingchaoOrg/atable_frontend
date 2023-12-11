<template>
  <div style="height: 100vh">
    <el-container style="height:100%; border: 1px solid #eee;">

      <el-aside :style="asideStyle" style="background-color: rgb(238, 241, 246)">
        <el-avatar class="button" src="https://cube.elemecdn.com/0/88/03b0d39583f48206768a7534e55bcpng.png"></el-avatar>

        <el-button class="button" @click="isCollapse = !isCollapse"
                   :icon="header_icon" circle>
        </el-button>

        <el-tooltip class="item" effect="dark" content="工作台" placement="left">
          <router-link to="/work">
            <el-button class="button"
                       icon="el-icon-house" circle>
            </el-button>
          </router-link>

        </el-tooltip>

        <el-tooltip class="item" effect="dark" content="通讯录" placement="left">
          <el-button class="button"
                     icon="el-icon-user" circle>
          </el-button>
        </el-tooltip>


        <el-tooltip class="item" effect="dark" content="模板中心" placement="left">
          <el-button class="button"
                     icon="el-icon-document-copy" circle>
          </el-button>
        </el-tooltip>

        <el-tooltip class="item" effect="dark" content="空间站设置" placement="left">
          <el-button class="button"
                     icon="el-icon-setting" circle>
          </el-button>
        </el-tooltip>


<!--        客服 搜索 通知 帮助 -->

        <div style="    position: fixed;    width: 60px;    bottom: 71px;background-color: aliceblue">
          <el-tooltip class="item" effect="dark" content="客服" placement="left">
            <el-button class="button"
                       icon="el-icon-phone-outline" circle>
            </el-button>
          </el-tooltip>
          <!--      搜索 -->
          <el-tooltip class="item" effect="dark" content="搜索" placement="left">
            <el-button class="button"
                       icon="el-icon-search" circle>
            </el-button>
          </el-tooltip>
          <!-- 通知 -->
          <el-tooltip class="item" effect="dark" content="通知" placement="left">

            <el-button class="button"
                       icon="el-icon-bell" circle>
            </el-button>
          </el-tooltip>

          <!-- 帮助 -->
          <el-tooltip class="item" effect="dark" content="帮助" placement="left">
            <el-button class="button"
                       icon="el-icon-warning-outline" circle>
            </el-button>
          </el-tooltip>
        </div>



      </el-aside>


      <el-container>
        <router-view :isCollapse="isCollapse" />


      </el-container>
    </el-container>
  </div>

</template>


<style lang="less">
.el-header {
  background-color: #B3C0D1;
  color: #333;
  line-height: 60px;
}


.el-menu-vertical-demo{
  height: 100%;
}

.el-aside {
  color: #333;
  .button{
    margin-top: 8px;
    margin-left: 10px
  }
}
.header1{
  min-height: 60px;
  background-color: #B3C0D1;
  color: #333;
}
</style>

<script>
export default {
  data() {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    };
    return {
      defaultOpen:['1', '3'],
      isCollapse: false,
      tableData: Array(20).fill(item)
    }
  },
  computed:{
    asideStyle(){
       return {
          width:"64px"
        }
    },
    asideStyle2(){
      return {
        width:"260px"
      }
    },
    headerStyle1(){
      if(this.isCollapse){
        return {
          width:"64px",
          height:"120px"
        }
      }
      return {
        width:"200px"
      }
    },
    headerStyle(){
      if(this.isCollapse){
        return {
          width:"64px"
        }
      }
      return {
        width:"146px"
      }
    },
    header_icon(){
      if(this.isCollapse){
        return "el-icon-s-unfold";
      }
      return "el-icon-s-fold";
    }
  }
};
</script>
