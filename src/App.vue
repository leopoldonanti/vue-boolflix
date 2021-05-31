<template>

  <div id="app">

    <HeaderComp
    @startSearc='startSearc' />
    <!-- all'attributo :titolo gli do il valore della variabile 'prova'  -->
    <MainComp :movies='risultatoFilm'
              :series='risultatoSerie'  />


  </div>

</template>

<script>

import axios from 'axios';
import HeaderComp from './components/HeaderComp.vue';
import MainComp from './components/MainComp.vue';


export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp,

  },
  data(){
    return{
      apiURL:'https://api.themoviedb.org/3/search/',
      api_key:'2dd500f967c4c76820bbd5604c59c34b',


      risultatoFilm:[],
      risultatoSerie:[],
    }
  },
  methods:{

    startSearc(obj){
      if(obj.type === 'all'){
        this.getAPI(obj.text, 'movie')
        this.getAPI(obj.text, 'tv')
      }else{
        this.getAPI(obj.text, obj.type)
      }
    },


    getAPI(query, type){
      axios.get(this.apiURL + type,{
        params:{
          api_key:this.api_key,
          query: query,
          language: 'it-IT'
        }
      })
      .then(res =>{
        console.log(res.data.results);
        if(type === 'movie'){
          this.risultatoFilm = res.data.results;
        }else{
          this.risultatoSerie = res.data.results;
        }
      })
      .catch(err =>{
        console.log(err);
      })
    }
  },
  created(){
    
  }
}
</script>

<style lang="scss">

@import '@/assets/style/general'

</style>
