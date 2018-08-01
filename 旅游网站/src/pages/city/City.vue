
<template>
	<div class="city">
		<city-header></city-header>
		<city-search :cities="cities"></city-search>
		<city-list :cities="cities" :hot="hotCities" :letter="letter"></city-list>
		<city-alphabet :cities="cities" @change="handelLeterChange"></city-alphabet>
	</div>
</template>

<script type="text/ecmascript-6">
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default{
	name:'City',
	data(){
		return{
			cities:{},
			hotCities:[],
			letter:''
		}
	},
	components:{
		CityHeader,
		CitySearch,
		CityList,
		CityAlphabet
	},methods:{
		getCityInfo(){
			axios.get('/api/city.json')
			.then(this.handleGetCityInfoSucc)

		},handleGetCityInfoSucc(res){
			res=res.data
			if(res.ret && res.data){
				const data=res.data
				this.cities=data.cities
				this.hotCities=data.hotCities
			}
		},handelLeterChange(letter){
			this.letter=letter

		}

	},mounted(){
		this.getCityInfo()

	}
}
</script>

<style lang="stylus" scoped>

</style>