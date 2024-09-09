# Salut Tes notes sur Vue.js Grosse merde

## Vue.js est un framework qui utilise javascript 

## Le router

```Javascript
import { createRouter, createWebHistory } from 'vue-router'
import Accueil from '../views/PageAccueil.vue'
import Catalogue from '../views/CatalogueView.vue'
import Personnalisation from '../components/Personnalisation.vue'
import Description from '../components/description.vue'
import Cart from '../components/cart.vue'

const router = createRouter({
  history: createWebHistory(import.meta.env.BASE_URL),
  routes: [
    {
      path: '/',
      name: 'Accueil',
      component: Accueil
    },
    {
      path:'/catalogue',
      name:'Catalogue',
      component: Catalogue
    },
    {
      path:'/Personnalisation',
      name:'Personnalisation',
      component: Personnalisation
    },
    {
      path:'/Description/:id',
      name:'Description',
      component: Description
    },
    {
      path:'/Cart',
      name:'Cart',
      component: Cart
    }
  ]
})

export default router
```

## Mise en place de L'app c'est par la que passe l'affichage des pages

```javascript

<script>
import  {RouterView}  from 'vue-router'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default{
  
    components:
    {
      Header,
      Footer,
   
    }
}
</script> 

<template>

  <Header />
  <router-view></router-view>
  <Footer />

  
</template>

<style>

</style>
```


## Les pages sont créér de la façon suivante
- le contenue qui ne changera pas est dans le dossier components
- Le contenue cqui change par chaque page est stocker dans le dossier views

## Exemple d'un components


```javascript
<script>
import { RouterLink } from 'vue-router';
export default{
  name:"PageAccueil"
}
</script>

<template>
<header>
<nav class="NavBar">
  <RouterLink to="/"><img id="LogoBeQueen" src="/public/logoBeQueenCut 1.png" alt="Logo Be-Queen"></RouterLink>
  <ul class="NavBar">
    <RouterLink to="/catalogue"><li>CATALOGUE</li></RouterLink>
    <RouterLink to="/Personnalisation"><li>PERSONNALISATION</li></RouterLink>
    <li>CONTACT</li>
    <RouterLink to="/Cart"><img src="/public/bag-check-fill 1.png" alt="Panier"></RouterLink>
    <li><img src="/public/user-solid 1.png" alt="User"></li>
</ul>
</nav>
</header>

</template>

<style>

.NavBar ul{
  list-style: none;
}

a{
  text-decoration: none;
  color: white
}
 .NavBar
 {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  width: 100%;
  background-color: #379777;
  padding-top: 1%;
  text-decoration: none;
  color: white;

 }

#LogoBeQueen
{
  position: relative;
  margin-left: 5%;
  margin-bottom: 5%;
  width: 15vh;
  height: 15vh;
}
.NavBar
{
  font-family: "Montserrat", sans-serif;
 
}

</style>
```
## Exemple d'une Views

```javascript
<script>
import ProductVue from '../components/catalogue.vue';

export default {
  components: {
    ProductVue
  },
  data() {
    return {


    }
  },
}
</script>
<template>



    <div id="carouselExample" class="carousel slide">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img src="/public/sunset-5033708_1280 1.png" class="d-block w-100" alt="...">
    </div>
    <div class="carousel-item">
      <img src="/public/bike-1505039_1280 1.png" class="d-block w-100 " alt="...">
    </div>
    <div class="carousel-item">
      <img src="/public/cycles-4254752_1280 1.png" class="d-block w-100" alt="...">
    </div>
  </div>
  <button class="carousel-control-prev" type="button" data-bs-target="#carouselExample" data-bs-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Previous</span>
  </button>
  <button class="carousel-control-next" type="button" data-bs-target="#carouselExample" data-bs-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="visually-hidden">Next</span>
  </button>
</div>



  <ProductVue />

</template>

<style scoped>
main {
  padding: 90px;
}

.image {
  width: 100%;
  height: 70vh;
  background-image: url('../../public/logo/bike-1505039_1280\ 1.png');
  background-size: contain;
}

h1 {
  position: absolute;
  top: 60%;
  font-size: 10rem;
  z-index: 1;
  color: var(--secondary);
  font-family: "MuseoModerno", sans-serif;
  font-weight: 500;

}

.footer-product {
  border-top: 5px solid var(--primary);
  margin: 6%;
  padding: 5rem 5rem 0 5rem;
}

.img1 {
  width: 100%;
  height: 75vh;
  align-content: center;
  background-image: url('../../public/image/Réparer-son-be-queen.png');
  background-repeat: no-repeat;
  background-size: contain;

  background-position: center;
  margin-bottom: 30px;
}

.img2 {
  width: 100%;
  height: 75vh;
  border-radius: 15px;
  background-image: url('../../public/image/nos-parcoure.png');
  background-repeat: no-repeat;
  background-size:cover;
  background-position: center;


}
</style>
```