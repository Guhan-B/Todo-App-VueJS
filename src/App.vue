<template>
  <div id="app">
    <div id="nav">
        <Header></Header>
        <div class="links">
          <router-link to="/">Home</router-link> |
          <router-link to="/about">About</router-link>
        </div>
    </div>
    <router-view/>
  </div>
</template>

<script>
import Header from './components/Header';

export default {
  name: 'App',
  components:{
    Header,
  }
}
</script>

<style>


#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.links{
    text-align: center;
    color: #2c3e50;
    padding: 1rem;
    text-transform: uppercase;
}
</style>

