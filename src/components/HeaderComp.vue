<template>
  
  <header>

    <div class="logotype">

      <h1>
        <img src="https://fontmeme.com/permalink/210528/323aa9a77404d38b71457254b1d10499.png" alt="netflix-font" border="0">
      </h1>

    </div>

    <div class="search-frame">

      <input v-model="textToSearch"
             type="text">

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
  border: none;
  color: rgb(233, 0, 0);
  font-family: 'roboto';
  text-align: center;
  font-size: 13px;
  letter-spacing: 0.5px;
  cursor: pointer;
}
.search-frame button:active{
  background-color: rgb(201, 201, 201);
}

</style>