<template>
	<ul class="list">
		<li class="item" v-for="item of letters" :key="item"
         @click="handleLeterClick" 
         @touchstart="handelTouchStart"
         @touchmove="handleTouchMove"
         @touchend="handleTouchEnd"
         :ref="item"
		>{{item}}</li>	
	</ul>

</template>

<script type="text/ecmascript-6">


export default{
	name:'Alphabet',
	data(){
		return {
			touchStatus:false,
			startY:0,
			timer:null
		}

	},
	props:{
		cities:Object
	},
	updated () {
		this.startY=this.$refs['A'][0].offsetTop
	
	},
	methods:{
		handleLeterClick(e){
			this.$emit('change',e.target.innerText)
		},
		handelTouchStart(){
			this.touchStatus=true

		},
		handleTouchMove(e){
			if(this.touchStatus){
				if(this.timer){
					clearTimeout(this.timer)
				}
				this.timer=setTimeout(()=>{
					const touchY=e.touches[0].clientY-79
					const index=Math.floor(((touchY-this.startY)/20))
					if(index>=0&& index<this.letters.length){
						this.$emit('change',this.letters[index])
					}
					console.log(index)
				},16)
			}

		},
		handleTouchEnd(){
			this.touchStatus=false

		}
	},computed:{
		letters(){
			const letters=[]
			for(let i in this.cities){
				letters.push(i)
			}
			return letters
		}
	}
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
	
	.list
		display :flex
		flex-direction :column
		justify-content :center
		position: absolute
		top:1.58rem
		right:0
		bottom:0
		width :.4rem
		.item
			text-align :center
			line-height :.4rem
			color :$bgColor
		



</style>