<template>
	<v-container style="margin-top: 10px; margin-bottom: 10px">
		<v-layout row wrap style>
			<details-card
				v-for="all in all"
				:id="all.isbn"
				:det="all.name"
				:naziv="all.name"
				:aut="all.authors"
				:key="all.isbn"
			/>
		</v-layout>
	</v-container>
</template>

<script>
	import axios from "axios";
	import DetailsCard from "@/components/DetailsCard.vue";
	export default {
		name: "Home",
		data() {
			return {
				all: [],
			};
		},
		async mounted() {
			const temp = await axios.get(
				"https://www.anapioficeandfire.com/api/books"
			);
			this.all = temp.data;
			console.log("api", this.all);
		},
		components: {
			DetailsCard,
		},
	};
</script>
