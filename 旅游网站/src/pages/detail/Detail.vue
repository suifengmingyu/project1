<template>
	<div>
		<detail-banner></detail-banner>
		<detail-header></detail-header>
		<div class="content"></div>
	</div>

</template>

<script type="text/ecmascript-6">

import DetailBanner from './components/Banner.vue'
import DetailHeader from './components/Header.vue'

export default{
	name:'Detail',
	components:{
		DetailBanner,
		DetailHeader
	}
}
</script>

<style lang="stylus" scoped>
	.content
		height :20rem

</style>