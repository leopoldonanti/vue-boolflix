<template>
  
  <header>

    <div class="logotype">

      <h1>
        <img src="https://fontmeme.com/permalink/210528/323aa9a77404d38b71457254b1d10499.png" alt="netflix-font" border="0">
      </h1>

    </div>

    <div class="search-frame">

      <input v-model="textToSearch"
             type="text"
             placeholder="cerca un film o una serie tv">

      <button @click="$emit('startSearc',{text:textToSearch, type:'all'})">
        CERCA</button>

      <button @click="$emit('startSearc',{text:textToSearch, type:'movie'})">
        CERCA FILM </button>
      
      <button @click="$emit('startSearc',{text:textToSearch, type:'tv'})">
        CERCA SERIE </button>
      
    </div>

  </header>

</template>

<script>
export default {
  name: 'HeaderComp',
  data(){
    return{
      textToSearch: '',
    }
  }
}
</script>


<style lang="scss" scoped>

header{
  width: 100%;
  background-color: rgb(29, 29, 29);
  color: rgb(233, 0, 0);
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  .logotype{
    width: 20%;
    display: flex;
    align-items: center;
    img{
      margin-left: 30px;
      width: 150px;
      cursor: pointer;
    }
  }
  .search-frame{
  width: 80%;
  height: 100px;
  display: flex;
  align-items: center;
  justify-content: flex-end;
  }
}
.search-frame input,.search-frame button{
  margin-right: 30px;
  padding: 10px 15px 10px 15px;
  border-radius: 20px;
  outline: none;
  font-family: 'roboto';
  text-align: left;
  font-size: 13px;
  letter-spacing: 0.5px;
  cursor: pointer;
}
  button{
    border: solid 1px white;
    color: white;
    background: transparent;
    &:active{
    background-color: rgb(220, 27, 40);
    border: solid 1px rgb(220, 27, 40);
    }
  }
  input{
    border: none;
  }

</style>