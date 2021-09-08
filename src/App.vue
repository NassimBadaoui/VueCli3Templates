<template>
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Link</a>
        </li>
        <li class="nav-item dropdown">
          <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
            Dropdown
          </a>
          <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
            <li><a class="dropdown-item" href="#"><router-link to="/test">Page test router</router-link></a></li>
            <li><a class="dropdown-item" href="#">Another action</a></li>
            <li><hr class="dropdown-divider"></li>
            <li><a class="dropdown-item" href="#">Something else here</a></li>
          </ul>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#" tabindex="-1" aria-disabled="false">Disabled</a>
        </li>
      </ul>
      <form class="d-flex">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <button class="btn btn-outline-success" type="submit">Search</button>
      </form>
    </div>
  </div>
  <router-view></router-view>

</nav>



  <inscrits :liste="personnes"></inscrits>

</template>

<script>
import Inscrits from './components/Inscrits.vue';
const Page1 = {
            template: '<div>Bienvenue sur la page 1</div>'
        }
const router = VueRouter.createRouter({
            history: VueRouter.createWebHistory(),
            routes: [
                { 
                    path: '/test', 
                    component: Page1
                }
            ]
        })
           
export default {
    name : 'App',
    components : {
        Inscrits
    },
    data (){
        return{
            personnes: [
                            { prenom: "Jean", nom: "Bréhat", age: 20 },
                            { prenom: "Léa", nom: "Prijean", age: 25 },
                            { prenom: "Chis", nom: "Martin", age: 38 },
                            { prenom: "Pierre", nom: "Petit", age: 18 },
            ],
        };
    }
}

</script>

<style>

</style>