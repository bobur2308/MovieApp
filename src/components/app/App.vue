<template>
  <div class="app font-monospace">
    <div class="content">
      <AppInfo :allMoviesCount="movies.length" :favMovCount="movies.filter(c=>c.favourite).length" />
      <div class="search-panel">
        <SearchPanel/>
        <AppFilter/>
      </div>
      <MovieList :movies="movies" />
      <MovieAddForm/>
    </div>
  </div>
</template>

<script>
import AppInfo from '@/components/app-info/AppInfo.vue';
import SearchPanel from '@/components/search-panel/SearchPanel.vue';
import AppFilter from '@/components/app-filter/AppFilter.vue';
import MovieList from '@/components/movie-list/MovieList.vue';
import MovieAddForm from '@/components/movie-add-form/MovieAddForm.vue';
import BtnClick from '../btn-click/BtnClick.vue';
export default{
  components:{
    AppInfo,
    SearchPanel,
    AppFilter,
    MovieList,
    MovieAddForm
  },
  data(){
    return {
      movies:[
        {
          name:"Omar",
          viewers:711,
          favourite:false,
          like:true
        },
        {
          name:"Empire of Osman",
          viewers:217,
          favourite:false,
          like:false
        },
        {
          name:"Ertugrul",
          viewers:710,
          favourite:true,
          like:false
        },
      ]
    }
  }
}

</script>

<style>
  .app{
    height: 100vh;
    color: black;
  }

  .content{
    width: 1000px;
    min-height: 700px;
    background-color: #fff;
    margin: 0 auto;
    padding: 5rem 10px;
  }
  .search-panel{
    margin-top: 2rem;
    padding: 1.5rem;
    background: #fcfaf5;
    border-radius: 4px;
    box-shadow: 15px 15px 15px rgba(0, 0, 0,0.15);
  }
</style>