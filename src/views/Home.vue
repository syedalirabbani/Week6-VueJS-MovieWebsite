<template>
  <div class="home container">
    <div class="row">
    <div class="col-9">
    <input type="text" placeholder="Enter movie name" class="form-control" v-model="userSearch">
    </div>
    <div class="col-3">
    <button class="btn btn-primary" style="width:100%;" v-on:click="searchPressed">Search</button>

    </div>
    </div>
    <hr>
    <div class="card" v-for="movie in searchResult" :key="movie.imdbId">
    <h3>{{movie.Title}}</h3>	
    </div>
    </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  data(){
  return {
  userSearch:'',
  searchResult:[]
  }
  },
  methods: {
  searchPressed:function(){
  fetch('http://www.omdbapi.com/?s='+this.userSearch+'&apikey=87d10179')
  .then(response => response.json())
  .then(data => this.searchResult = data["Search"]);
  }
  }
  
}
</script>
