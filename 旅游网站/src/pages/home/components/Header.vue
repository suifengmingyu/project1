<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon" >&#xe624;</div>
		</div>
		<div class="header-input">
			<span class="iconfont">&#xe632;</span>
		输入城市/景点/游玩主题</div>
		<div class="header-right">城市
			<span class="iconfont arrrow-icon">&#xe6aa;</span></div>

	</div>
</template>

<script type="text/ecmascript-6">
export default{
  name:'Header'
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
   display: flex
   line-height : .86rem
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
   	  width : 4.2em
   	  float :right
   	  text-align center
   	  .arrrow-icon
   	  	margin-left : -.04rem
   	  	font-size : .30rem

   



</style>
