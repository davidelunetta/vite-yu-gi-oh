<template>
    <header>
        <div class="d-flex justify-content-between">
            <img src="/yu-gi-oh-logo-1.png" alt="logo" class="py-3 ps-4">
        </div>
       
    </header>
</template>

<script>
import { store } from "../data/store";
export default{
    name:'HeaderComponent',

    data(){
        return{
            store,
        }
    },
}
</script>

<style lang="scss" scoped>
    img{
        width: 180px;
    }
</style>