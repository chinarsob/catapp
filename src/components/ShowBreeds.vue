<template>
    <div class = "card">
        <img alt="No Image" :src="imgSrc" />
        <div class = "name"> {{ showName }} </div>
        <div class = "origin"> <span class="name">Origin : </span>{{ showOrigin}} </div>
        <div class = "desc"> {{ showDesc }}</div>
    </div>    
</template>
<script>
export default{
    props : {
        breeds : {
            type: Object,
            Required:true
        }
    },
    computed: {
        showName() {
            return this.breeds.name;
        },
        showDesc() {
            return this.breeds.description;
        },
        imgSrc() {
            return this.breeds.image?.url;
        },
        showOrigin() {
            return this.breeds.origin;
        }
    }
}
</script>
<style scoped>
.card {
	display: flex;
	flex-direction: column;
	width: 315px;
	height: 512px;
	margin: 12px;
	border-radius: 13px;
    border: solid 1px #ececec;
	/* box-shadow: 1 1px 1px rgb(255 255 255); */
}
.name {
    margin-top: 10px;
    font-weight: bold;
}
.desc {
    padding: 5px;
    overflow: scroll;
    text-align: justify;
}
img {
	border-top-left-radius: 12px;
    border-top-right-radius: 12px;
}
</style>