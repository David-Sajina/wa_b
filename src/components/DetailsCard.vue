<template>
	<v-layout row wrap style>
		<v-card
			class="text-xs-center ma-3"
			max-width="350"
			style="margin-top: 15px"
		>
			<v-card-title> {{ id }} </v-card-title>
			<v-card-subtitle> {{ det }} </v-card-subtitle>
			<v-card-subtitle> {{ aut[0] }} </v-card-subtitle>
			<v-card-actions>
				<router-link :to="{ name: 'Details', params: { isbn: id } }">
					<v-btn rounded color="primary" dark>Details</v-btn>
				</router-link>
			</v-card-actions>
		</v-card>
	</v-layout>
</template>
<script>
	export default {
		name: "DetailsCard",
		props: {
			id: String,
			det: String,
			aut: [],
		},
	};
</script>

<style></style>
