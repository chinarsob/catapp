<template>
<div>
    <h1> Cat Breeds </h1>
    <div class="show-list">
        <div v-for = "res in result"
        :key = "res.id">
            <show-breeds :breeds = "res" />
        </div>    
    </div>
</div>
</template>
<script>
import ShowBreeds from "./ShowBreeds.vue"
export default{
    components: {
        ShowBreeds
    },
    data() {
        return {
            result: {},
            error: null
        }
    },
    mounted() {
        this.fetchBreeds();
    },

    methods: {
		fetchBreeds() {
			// Fetch Breeds
			fetch("https://api.thecatapi.com/v1/breeds",{
                headers:
                { "x-api-key" : "9d28fed9-da38-4f14-a4af-8aae646d14fa" }
            })
			.then(response =>
				response.json()
			)
			.then(data => {
				//this.isLoading = false;
				this.result = data;
                console.log(this.result);
			}).catch(() => {
				//this.isLoading = false;
				this.error = "Please try later";
			});
		}
	}
}
</script>

<style scoped>
.header {
	margin-bottom: 18px;
}

.show-list {
	display: flex;
	flex-direction: row;
	flex-wrap: wrap;
	justify-content: center;
}
</style>