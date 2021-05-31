<template>

  <main>
    <div class="container">

      <h1>{{titles[type]}}</h1>


      <div  v-for="movie in movies"
            :key="movie.id"
            class="card">
        <h4>{{movie.title}}</h4>
        <h4>{{movie.original_title}}</h4>
        <h5>{{movie.original_language}}</h5>
        <h5>{{movie.vote_average}}</h5>

        
      </div>

      

    </div>
  </main>
</template>

<script>
export default {
  name: 'MainComp',
  props:{
    movies: Array,
    series: Array,
  },
  data(){
    return{
      titles:{
        'movies':'film trovati',
        'series': 'serie trovate'
      }
    }
  }
  
}
</script>

<style lang="scss">
  main{
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    .container{
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      padding: 20px;
      margin-top: 30px;
      .card{
        width: 200px;
        height: 300px;
        border: solid 1px rgb(232, 232, 232);
        margin: 20px;
        border-radius: 5px;
        padding: 0px 10px 0 10px;
        line-height: 20px;
        display: flex;
        flex-direction: column;
        cursor: pointer;
        transition: all 0.2s;
        &:hover{
        -webkit-box-shadow: -10px 0px 13px -7px #000000, 10px 0px 13px -7px #000000, 5px 5px 15px 5px rgba(0,0,0,0); 
        box-shadow: -10px 0px 13px -7px #000000, 10px 0px 13px -7px #000000, 5px 5px 15px 5px rgba(0,0,0,0);
        
        }
        h5{
         text-transform: uppercase;
        }
        
      }
    }
  }



</style>