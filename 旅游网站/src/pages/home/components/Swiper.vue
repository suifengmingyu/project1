<template>
	<div class="wrapper">
		<swiper :options="swiperOption" >
			<!-- slides -->
			<swiper-slide>
				<img class="swipe-img" src="http://img1.qunarzz.com/piao/fusion/1807/71/e4bf6ce2a203ba02.jpg_750x200_c99e3a64.jpg">
			</swiper-slide>
			<swiper-slide>
				<img class="swipe-img" src="http://img1.qunarzz.com/piao/fusion/1807/c6/44fce1467be17702.jpg_750x200_406f5fc3.jpg" >
			</swiper-slide>
			<swiper-slide>
				<img class="swipe-img" src="http://img1.qunarzz.com/piao/fusion/1807/e7/d70d0830a9941b02.jpg_750x200_f8c7d2ad.jpg" >
			</swiper-slide>
			<swiper-slide class="swipe-img">
				<img class="swipe-img" src="http://img1.qunarzz.com/piao/fusion/1806/3c/c72a1ccd4d7b2202.jpg_750x200_b88bbab4.jpg" />
			</swiper-slide>

			<div class="swiper-pagination"  slot="pagination"></div>

		</swiper>
	</div>
</template>




 <style lang="stylus" scoped>
    /*样式穿透，不收scoped限制，修改wrapper下所有应用swiper-pagination-bullet-active
    	样式的子组件的样式*/
   .wrapper >>> .swiper-pagination-bullet-active
 	  background :#fff
   .wrapper
      overflow:hidden
      width:100%
      height :0
      padding-bottom: 31.25%
      background:#eee
      .swipe-img
         width:100%

</style>
 
<script  type='text/ecmascript-6'>
export default {
	name:'HomeSwiper',
	data() {
		return {
			swiperOption: {
				    pagination:'.swiper-pagination',//显示页码
                    initialSlide:0,//设定初始化时slide的索引
                    direction:'horizontal',//Slides的滑动方向，可设置水平(horizontal)或垂直(vertical)。
                    loop: true,  //无限滚动
                    speed:800,//滑动速度
                    autoplay:1500,//自动切换的时间间隔
                    onSlideChangeEnd: swiper => { //滑动之后回调函数
                        //切换结束时，告诉我现在是第几个slide
                        //console.log('onSlideChangeEnd', swiper.realIndex)
                    }
                }
            }
        }
    }

</script>