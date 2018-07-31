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

                }
            }
        },props:{
            list:Array
        }
        ,computed:{
        	/*计算分页*/
        	pages (){
        		const pages=[]
        		this.list.forEach((item,index)=>{
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
