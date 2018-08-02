<template>
	<div>
		<div class="title">热销推荐</div>
		<ul >

			<router-link  tag='li' class="item border-bottom" v-for="item in list" :key="item.id" :to="'/detail/'+item.id">
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
					<button class="item-button">查看详情</button>
				</div>
				
			</router-link>>
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
			recommendList:[{
				id:'0001',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_200x200_c118d7da.jpg',
				title:'广州长隆旅游度假区',
				desc:'来广州来长隆，就对了，就够了~'
			},{
				id:'0002',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_200x200_ea02ef99.jpg',
				title:'长隆野生动物世界',
				desc:'来广州来长隆，就对了，就够了~'
			},{
				id:'0003',
				imgUrl:'http://img1.qunarzz.com/sight/p0/1507/9e/7b5e0a44cb0310280b1aeb2a8dd94de8.water.jpg_200x200_3c429960.jpg',
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
    margin-top: .2rem
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>

