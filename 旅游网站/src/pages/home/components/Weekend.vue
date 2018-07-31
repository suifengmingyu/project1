<template>
	<div>
		<div class="title">周末去哪</div>
		<ul >
			<li class="item border-bottom" v-for="item in list" :key="item.id">
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
	props:{
		list:Array
	}
	/*data(){
		return {
			weekendList:[{
				id:'0001',
				imgUrl:'http://img1.qunarzz.com/sight/source/1606/88/56f7f4bd0493fe.jpg_r_640x214_f8c0994a.jpg',
				title:'广州长隆旅游度假区',
				desc:'来广州来长隆，就对了，就够了~'
			},{
				id:'0002',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_600x330_b5e86902.jpg',
				title:'长隆野生动物世界',
				desc:'来广州来长隆，就对了，就够了~'
			},{
				id:'0003',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1507/9e/7b5e0a44cb0310280b1aeb2a8dd94de8.water.jpg_600x330_bfb39f14.jpg',
				title:'长隆国际大马戏剧院',
				desc:'来广州来长隆，就对了，就够了~'
			}
			]
		}
	}*/
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item-img-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 37.09%
    .item-img
      width: 100%
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
