<template>
	<div class="list" ref="wrapper">
		<div>
			<div class="area">
				<div class="title border-topbottom">当前城市</div>
				<div class="button-list">
					<div class="button-wrapper">
						<div class="button">
							{{this.currentCity}}
						</div>
					</div>
				</div>
			</div>
			<div class="area">
				<div class="title border-topbottom">热门城市</div>
				<div class="button-list">
					<div class="button-wrapper" v-for="item in hot" :key="item.id"
					@click="handleCityClick(item.name)">
						<div class="button">
							{{item.name}}
						</div>
					</div>
					

				</div>
			</div>

			<div class="area" v-for="(item,key) in cities" :key="key" :ref="key">
				<div class="title border-topbottom">{{key}}</div>
				<div class="item-list">
					<div class="item border-bottom" v-for="innerItem in item " :key="innerItem.id" @click="handleCityClick(innerItem.name)">{{innerItem.name}}</div>
				</div>
			</div>
		
		</div>
	</div>
</template>

<script type="text/ecmascript-6">
import Bscroll from 'better-scroll'
import {mapState,mapMutations} from 'vuex'
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
import router from 'vue-router'
export default{
	name:'CityList'
	,computed:{
		...mapState({
			currentCity:'city'
		})


	}
	,mounted(){
		this.scroll=new Bscroll(this.$refs.wrapper)
	},props:{
		hot:Array,
		cities:Object,
		letter:String

	},methods:{
		handleCityClick(city){
			
			this.changeCity(city)
			this.$router.push('/')
		},
		...mapMutations(['changeCity'])//将mutations的changeCity方法映射过来
	}
	,watch:{
		letter (){
			if(this.letter){
				const element=this.$refs[this.letter][0]
				this.scroll.scrollToElement(element)
			}		
		}
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