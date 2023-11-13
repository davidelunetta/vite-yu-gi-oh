<template>
    <div>
        <figure><img :src="img" alt="img"></figure>
        <h5>Name: {{ name }}</h5>
        <div>Type: {{ type }}</div>
        <div>Frame Type: {{ frameType }}</div>
        <div>Description: {{ desc }}</div>
    </div>
</template>

<script>
export default{
    name:'CardComponent',
    props:{
        img:String,
        name:String,
        type:String,
        frameType:String,
        desc:String,
    },
    data(){
        return{
        }
    }
}
</script>

<style lang="scss" scoped>
    
</style>