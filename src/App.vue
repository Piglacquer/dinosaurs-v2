<template>
  <div id="app">
    <Header></Header>
    <main>
      <h2>Profiles</h2>
        <ul>
          <Profile v-for='dinosaur in dinosaursData' v-bind:dinosaur='dinosaur' :key='dinosaur.name'></Profile>
        </ul>
    </main>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from './components/Header'
import Profile from './components/Profile'
import SkillList from './components/SkillList'
import Footer from './components/Footer'

export default {
  name: 'App',
  data() {
    return {
      dinosaursData: [],
      apiUrl:'../static/dinosaurs.json'
    }
  },
  components: {
    Header,
    Profile,
    SkillList,
    Footer
  },
  mounted() {
    fetch(this.apiUrl)
    .then(response => response.json())
    .then(response => {
      this.dinosaursData = response
    })
  }
}</script>

<style>

html {
	margin: 0;
	padding: 0;
}

ul{
  list-style: none;
}

body {
	margin: 0 30px 0 30px;
	padding: 0;
	font-family: sans-serif;
	color: #1b997a;
	display: grid;
	grid-template-rows: 15% 75% 10%;
}

main {
  grid-row: 2/3;
}

main section {
  padding: 0 20px 0 20px;
  display: grid;
  grid-template-columns: repeat(auto-fit, x100%);
  grid-gap: 10px;
  margin: 0 auto;
  width: 50%;
}

small {
  color: black;
  font-size: .5rem;
  margin-left: 10px;
}

p {
  font-size: .8rem;
}
</style>
