<template>
	<div>
		<div class="title">周末去哪</div>
		<ul >
			<li class="item border-bottom" v-for="item in recommendList" :key="item.id">
				<div class="item-img-wrapper">
					<img class="item-img" :src='item.imgUrl'>
				</div>
				<div class="item-info">
					<p class="item-title" >
						{{item.title}}
					</p>
					<p class="item-desc">
						{{item.desc}}
					</p>
				</div>
				
			</li>
		</ul>
	</div>
</template>

<script type="text/ecmascript-6">
export default{
	name:'HomeRecommend',
	data(){
		return {
			recommendList:[{
				id:'0001',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_200x200_c118d7da.jpg',
				title:'广州长隆旅游度假区',
				desc:'来广州来长隆，就对了，就够了~'
			},{
				id:'0002',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_200x200_c118d7da.jpg',
				title:'广州长隆旅游度假区',
				desc:'来广州来长隆，就对了，就够了~'
			},{
				id:'0003',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_200x200_c118d7da.jpg',
				title:'广州长隆旅游度假区',
				desc:'来广州来长隆，就对了，就够了~'
			}
			]
		}
	}
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
.title
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
.item-img-wrapper
	overflow :hidden
	height :0
	padding-bottom :33.9%
	.item-img
		width :100%
.item-info
  padding: .1rem
  .item-title
    line-height: .54rem
    font-size: .32rem
    ellipsis()
  .item-desc
    line-height: .4rem
    color: #ccc
    ellipsis()
</style>

