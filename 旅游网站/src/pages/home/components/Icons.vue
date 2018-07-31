<template>
	<div class="icons">
		<swiper :options="swiperOption" >
			<swiper-slide v-for="(page,index) of pages" :key="index">
				<div class="icon" v-for="item of page"
				:key="item.id">
					<div class="icon-img">
						<img class="icon-img-content" :src='item.imgUrl'>
					</div>
					<div class="icon-desc"><p >{{item.desc}}</p></div>
				</div>
			</swiper-slide>
			
		</swiper>
		
	
	</div>
	
</template>


<script type="text/ecmascript-6">
export default{
	name:'HomeIcons',
	data() {
		return {
			swiperOption: {
				    pagination:'.swiper-pagination',//显示页码
                    loop: false,  //无限滚动
                    autoplay:false,//自动切换的时间间隔

                },
                iconList:[{
                	id:'0001',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
                	desc:'景点门票'
                },{
                	id:'0002',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
                	desc:'广州必游'
                },{
                	id:'0003',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
                	desc:'动植物园'
                },
                {
                	id:'0004',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
                	desc:'游乐场'
                },{
                	id:'0005',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png',
                	desc:'游船游艇'
                },{
                	id:'0006',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
                	desc:'夏日玩水'
                },{
                	id:'0007',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png',
                	desc:'城市观光'
                },
                {
                	id:'0008',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
                	desc:'汽车票'
                },{
                	id:'0009',
                	imgUrl:'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png',
                	desc:'玩转长隆'
                }
                ]

            }
        },computed:{
        	/*计算分页*/
        	pages (){
        		const pages=[]
        		this.iconList.forEach((item,index)=>{
        			const page=Math.floor(index/8)/*index为数据位置，结果为0，即第0页有八条数据*/
        			if(!pages[page]){
        				pages[page]=[]
        			}
        			pages[page].push(item)/*添加每一页数据*/
        		})
        		return pages

        	}
        }
    }
    </script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: .1rem
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: .44rem
        box-sizing: border-box
        padding: .1rem
        .icon-img-content
          display: block
          margin: 0 auto
          height: 100%
      .icon-desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height: .44rem
        line-height: .44rem
        text-align: center
        color: $darkTextColor
        ellipsis()
        
        
</style>
