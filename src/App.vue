<template>
	<div class="App">
		<div class="header">  
			<h1 style="font-size: 24px;">hello there, Human!</h1>
			<div style="display: flex;">
				<svg style="margin-right: 20px;" xmlns="http://www.w3.org/2000/svg" width="30" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
					<path stroke-linecap="round" stroke-linejoin="round" d="M12 7.5h1.5m-1.5 3h1.5m-7.5 3h7.5m-7.5 3h7.5m3-9h3.375c.621 0 1.125.504 1.125 1.125V18a2.25 2.25 0 0 1-2.25 2.25M16.5 7.5V18a2.25 2.25 0 0 0 2.25 2.25M16.5 7.5V4.875c0-.621-.504-1.125-1.125-1.125H4.125C3.504 3.75 3 4.254 3 4.875V18a2.25 2.25 0 0 0 2.25 2.25h13.5M6 7.5h3v3H6v-3Z" />
				</svg>
				<svg xmlns="http://www.w3.org/2000/svg" width="30" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
					<path stroke-linecap="round" stroke-linejoin="round" d="M14.857 17.082a23.848 23.848 0 0 0 5.454-1.31A8.967 8.967 0 0 1 18 9.75V9A6 6 0 0 0 6 9v.75a8.967 8.967 0 0 1-2.312 6.022c1.733.64 3.56 1.085 5.455 1.31m5.714 0a24.255 24.255 0 0 1-5.714 0m5.714 0a3 3 0 1 1-5.714 0" />
				</svg>
			</div>
    	</div>
	
		<!-- <div v-for="job in jobs" :key="job.id">
			<p>{{ job.title }} - {{ job.location }} - {{ job.salary }}</p>
		</div> -->
		
		<!-- <button @click="changeName('juswa'), changeAge('25')"></button> -->
		<!-- {{ name }} - {{ age }} -->
		<div class="components">
			<router-view :jobs="jobs"/>
		</div>
		
		<!-- <HomeComp :jobs="jobs"/> -->
	</div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue';
import HomeComp from './components/HomeComp.vue';
import type Job from './types/Job';

export default defineComponent({
	name: 'App',
	components: { HomeComp },

	setup() {
		/*
			interface types 3
		*/
		const jobs = ref<Job[]>([
			{ title: 'Farm Worker', location: 'lon-lon ranch', salary: 10000, id: '1'},
			{ title: 'Flavor Scientist', location: 'US based company', salary: 60000, id: '2'},
			{ title: 'Coach', location: 'Somewhere near', salary: 15000, id: '3'},
			{ title: 'Wood Cutter', location: 'Somewhere far', salary: 50000, id: '4'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'},
			{ title: 'Grass Cleaner', location: 'house', salary: 80000, id: '5'}
		])

		return { jobs }

		/*
			reactive 1
		*/
		// const state = reactive({
		// 	name: 'Link',
		// 	age: 25 as string | number //Type Assertion
		// })

		// state.name = ''
		// state.age = 0
		// return { 
		// 	...toRefs(state)
		// }

		/*
			Refs 2
		*/
		// const name = ref('Link');
		// const age = ref<number | string>(25); //Generic arguments

		// return { name, age }
	},

	// data(){
	// 	return {
	// 		name: 'Josh',
	// 		age: 18 as string | number
	// 	}
	// },
	// methods: {
	// 	changeName(name: string){
	// 		this.name = name;
	// 		return name;
	// 	},
	// 	changeAge(age: string | number){
	// 		this.age = age;
	// 		return age;
	// 	}
	// },
});
</script>

<style>
	.App {
		display: flex; 
		flex-direction: column;
		height: 100vh;
	}
	
	.header {
		display: flex;
		justify-content: space-between;
		flex: 0 0 5%;
		background-color: #dfddc8; 
		padding: 10px 50px;
		text-align: left; 
		border-bottom: 2px solid;
		position: sticky;
		top: 0;
	}
	
	.components {
		flex: 1; 
		background-color: #dfddc8;
		padding: 20px;
	}
</style>

