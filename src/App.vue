<template>
  <HeaderComponent/>
  <div class="container-fluid">
    <div class="row">
            <div v-for="(character, index) in store.characterList" :key="character.id" class="col-3 p-3 my-card">
              <CardComponent
                :img="character.card_images[0].image_url_small"
                :type="character.type"
                :name="character.name"
                :frameType="character.frameType"
                :desc="character.desc"
              />  
            </div>
    </div>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import { store } from "./data/store";
import axios from 'axios';
import CardComponent from "./components/CardComponent.vue";
export default {
    name: 'App',
    components:{
        HeaderComponent,
        CardComponent,
    },
    data(){
        return{
            store
        }
    },
    methods:{
        change(){
            this.store.title= 'new title'
        },
        getCharacters(){
            const url = store.apiUrl;
            axios.get(url).then((response)=>{
                store.characterList = response.data.data;
                console.log(response.data);
            });
        }
    },
    created(){
        this.getCharacters();
    }
}
</script>

<style lang="scss" scoped>
  
</style>