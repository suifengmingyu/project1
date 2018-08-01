<template>
	<div class="list" ref="wrapper">
		<div>
			<div class="area">
				<div class="title border-topbottom">当前城市</div>
				<div class="button-list">
					<div class="button-wrapper">
						<div class="button">
							北京
						</div>
					</div>
				</div>
			</div>
			<div class="area">
				<div class="title border-topbottom">热门城市</div>
				<div class="button-list">
					<div class="button-wrapper" v-for="item in hot" :key="item.id">
						<div class="button">
							{{item.name}}
						</div>
					</div>
					

				</div>
			</div>

			<div class="area" v-for="(item,key) in cities" :key="key">
				<div class="title border-topbottom">{{key}}</div>
				<div class="item-list">
					<div class="item border-bottom" v-for="innerItem in item " :key="innerItem.id">{{innerItem.name}}</div>
				</div>
			</div>
		
		</div>
	</div>
</template>

<script type="text/ecmascript-6">
import Bscroll from 'better-scroll'
/*
better-scroll要求,三层结构,最后一层平级结构
<div ref="warpper">
	<div>
		<div>
		</div>
		<div>
		</div>
	</div>
</div>

*/
export default{
	name:'CityList'
	,mounted(){
		this.scroll=new Bscroll(this.$refs.wrapper)
	},props:{
		hot:Array,
		cities:Object

	}
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
	
	.border-topbottom
		&:before
			border-color :#ccc
		&:after
			border-color :#ccc
	.border-bottom
		&:before
			border-color :#ccc
	.list
		overflow:hidden
		position :absolute
		top:1.58rem
		left:0
		right:0
		bottom :0
	
		.title
			line-height :.54rem
			background-color :#eee
			padding-left:.2rem
			color:#666
			font-size :.26rem
		.button-list
			padding :.1rem .6rem .1rem .1rem
			overflow :hidden
			.button-wrapper
				float :left
				width :33.33%
				.button
					padding:.1rem 0
					margin:.1rem
					text-align :center
					border:.02rem solid #ccc
					border-radius :.06rem
		.item-list
			.item
				line-height :.76rem
				color :#666
				padding-left :.2rem

</style>