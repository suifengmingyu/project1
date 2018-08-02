<template>
	<div>
		<detail-banner></detail-banner>
		<detail-header></detail-header>
		<detail-list :list="list"></detail-list>
		<div class="content"></div>
	</div>

</template>

<script type="text/ecmascript-6">

import DetailBanner from './components/Banner.vue'
import DetailHeader from './components/Header.vue'
import DetailList from './components/List.vue'

export default{
	name:'Detail',
	components:{
		DetailBanner,
		DetailHeader,
		DetailList
	},data(){
		return{
			list:[{
				title:'成人票',
				children:[{
					title:'成人票二级联票',
					children:[{
						title:'成人票三级联票'
						
					}]
				},{
					title:'成人票三级联票'
				}]
			},{
				title:'学生票'
			},{
				title:'儿童票'
			},{
				title:'特惠票'
			}]
		}
	}
}
</script>

<style lang="stylus" scoped>
	.content
		height :20rem

</style>