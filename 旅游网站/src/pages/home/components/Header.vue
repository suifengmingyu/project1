<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon" >&#xe624;</div>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
		输入城市/景点/游玩主题</div>
    <router-link  to="/city">
      <div class="header-right">
        {{this.city}}
       <span class="iconfont arrrow-icon">&#xe6aa;</span>
     </div>
   </router-link>
 </div>
</template>

<script type="text/ecmascript-6">
import {mapState} from 'vuex'
export default{
  name:'HomeHeader',
  computed:{
    ...mapState(['city']),//把state的city属性映射到mapState
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
   display: flex
   line-height : $headerHeight
   background : $bgColor
   color : #fff
   .header-left
       width: .64rem
       float:left
       .back-icon
         text-align :center
         font-size :.4rem
      
   .header-input
      flex : 1
      background #fff
      border-radius 5px
      height .64rem
      line-height : .64rem
      margin-top .12rem
      margin-left .24rem
      color #ccc
      padding-left : .2rem
      
   .header-right
   	  mian-width : 1.04em
      padding:0 .1rem
   	  float :right
   	  text-align center
      color:#fff
   	  .arrrow-icon
   	  	margin-left : -.04rem
   	  	font-size : .30rem
 
</style>
