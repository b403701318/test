<template>
  <div class="tab_bar_item" @click="itemClick">
    <div v-if="!isActive"><slot name="item-icon"></slot></div>
    <div v-else><slot name="item-icon-active"></slot></div>
    <div :style="activeStyle"><slot name="item-text"></slot></div>
  </div>
</template>

<script>
export default {
  name: "TabBarItem",
  props:{
    path:String,
    activeColor: {
      type:String,
      default:'red'
    }
  },
  data(){
    return{
      //isActive:true,
    }
  },
  computed:{
    isActive(){
      //this.$route.path处于活跃路由的path
      //console.log(this.$route.path)
      //indexOf    this.$route.path是否包含this.path，如果包含就不等于-1
      return this.$route.path.indexOf(this.path) !== -1
    },
    activeStyle(){
      return this.isActive ?{color:this.activeColor} : {}
    }
  },
  methods:{
    itemClick(){
     // console.log(this.$route.path)
      //console.log(this.path)
      this.$router.replace(this.path)
    }
  }
}
</script>

<style scoped>
.tab_bar_item{
  flex: 1;
  text-align: center;
  height: 49px;
  font-size: 14px;
  margin-top: 3px;
  vertical-align: middle;/*去掉图片下边的3个像素*/
  margin-bottom: 2px;
}
.tab_bar_item img{
  width: 24px;
  height: 24px;
}
/*.active{*/
/*  color: red;*/
/*}*/
</style>