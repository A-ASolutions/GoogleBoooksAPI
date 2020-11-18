<template>
       <ol class="search-results">
      <li class="search-result" v-for="book in searchResults.items" :key="book.id">
        <img :src="'http://books.google.com/books/content?id=' + book.id + '&printsec=frontcover&img=1&zoom=1&edge=curl&source=gbs_api'" class="search-result--thumbnail">
      
        <div class="item-info">
          <h3>{{ book.volumeInfo.isbn }}</h3>
          <h3>{{ book.volumeInfo.title }}</h3>
          <h4 v-if="book.volumeInfo.authors">by {{ bookAuthors(book) }}</h4>
         <h3>{{ book.volumeInfo.description }}</h3>
       
        </div>
      </li>
    </ol>  

</template>

<script>
 export default {
     name:'searchForm',
 
 data() {
      return {
      showModal: true
      }
      }  
 }
</script>
<style>
  input[type=text], select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}
button {
    color: #444444;
    background: #F3F3F3;
    border: 1px #DADADA solid;
    padding: 5px 10px;
    border-radius: 2px;
    font-weight: bold;
    font-size: 9pt;
    outline: none;
}

button:hover {
    border: 1px #C6C6C6 solid;
    box-shadow: 1px 1px 1px #EAEAEA;
    color: #333333;
    background: #F7F7F7;
}

button:active {
    box-shadow: inset 1px 1px 1px #DFDFDF;   
}


</style>