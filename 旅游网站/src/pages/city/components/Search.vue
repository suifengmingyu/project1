<template>
	<div>
		<div class="search">
			<input class="search-input" type="text" placeholder="输入城市名或拼音" v-model="keyword">

		</div>
		<div class="search-content" ref="search" v-show="keyword">
			<ul>
				<li v-for="item of list" class="search-item border-bottom" :key="item.id"
				@click="handleCityClick(item.name)">
					{{item.name}}
				</li>
				<li class="search-item border-bottom" v-show="hasNoList">
					没有找到匹配数据
				</li>
			</ul>


		</div>
	</div>
</template>

<script type="text/ecmascript-6">
import {mapMutations} from 'vuex'
import Bscroll from 'better-scroll'
export default{
	name:'CitySearch',
	data(){
		return {
			keyword:'',
			list:[],
			timer:null
		}
	},props:{
		cities:Object
	},
	mounted(){
		this.scroll=new Bscroll(this.$refs.search)


	}
	,watch: {
		keyword () {
			
			if (this.timer) {
				clearTimeout(this.timer)
			}
			if (!this.keyword) {
				this.list = []
				return
			}
			this.timer = setTimeout(() => {
				const result = []
				for (let i in this.cities) {
					this.cities[i].forEach((value) => {
						if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
							result.push(value)
						}
					})
				}
				this.list = result
			}, 100)
		}
	},computed:{
		hasNoList(){
			return !this.list.length
		}
	},methods:{
			handleCityClick(city){
			
			this.changeCity(city)
			this.$router.push('/')
		},
		...mapMutations(['changeCity'])
	}
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'

.search
	height :.72rem
	padding:0 .1rem
	background-color :$bgColor
	.search-input
		box-sizing:border-box
		width:100%
		height:.62rem
		line-height :.62rem
		text-align :center
		border-radius :.06rem
		padding:0 .2rem
		color:#666
.search-content
	    z-index: 1
	    overflow: hidden
	    position: absolute
	    top: 1.58rem
	    left: 0
	    right: 0
	    bottom: 0
	    background: #eee
	    .search-item	
		      line-height: 0.62rem
		      padding-left: 0.2rem
		      color:#666
		      background-color:#fff	
	    		


</style>