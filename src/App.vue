<template>
<div>
   <mdb-navbar color="indigo" position="top" light expand="small">
      <router-link to="/">
         <mdb-navbar-brand class="navbar-brand" href="https://mdbootstrap.com/">
            Pizza House
         </mdb-navbar-brand>
      </router-link>
      <mdb-navbar-toggler class="navbar-collapse collapse">
         <mdb-navbar-nav class="navbar-nav ml-auto" right>
            <router-link to="/menu">
               <mdb-nav-item class="nav-link">Menu</mdb-nav-item>
            </router-link>
            <router-link to="/learn">
               <mdb-nav-item class="nav-link">Learn</mdb-nav-item>
            </router-link>
            <router-link to="/about">
               <mdb-nav-item class="nav-link">About</mdb-nav-item>
            </router-link>
         </mdb-navbar-nav>
      </mdb-navbar-toggler>
   </mdb-navbar>

   <center>
      <div class="line"></div>
      <br>
   </center>


   <div id="page-container">
      <div id="content-wrap">
         <router-view />

      </div>
      <footer id="footer">
         <br>
         <center>
            <p id="footer-header">Pizza House</p>
            <p class="footer-menu">
               <router-link to="/">
                  <a class="footer-link" href="">Home</a>
               </router-link>
               |
               <router-link to="/menu">
                  <a class="footer-link" href="">Menu</a>
               </router-link>
               |
               <router-link to="/learn">
                  <a class="footer-link" href="">Learn</a>
               </router-link>
               |
               <router-link to="/about">
                  <a class="footer-link" href="">About</a>
               </router-link>
            </p>
            <p id="source-code-link">Find source code <a href="https://github.com/kyleokolowitz/pizzahouse2">here.</a></p>
         </center>
      </footer>
   </div>
</div>
</template>

<script>
import {
   mdbNavbar,
   mdbNavbarBrand,
   mdbNavbarToggler,
   mdbNavbarNav,
   mdbNavItem
} from 'mdbvue';

export default {
   name: 'App',
   components: {
      mdbNavbar,
      mdbNavbarBrand,
      mdbNavbarToggler,
      mdbNavbarNav,
      mdbNavItem
   },
   props: {
      pizzas: Array
   }
}
</script>

<style>
:root {
   --white: #fffcf9;
   /* white with orange*/
   --light-rust: #dd7804;
   --rust: #C55829;
}

/* General */
body {
   font-family: Papyrus;
   background-color: var(--white);
   position: relative;
}

.nav-item {
   font-size: 20px;
   color: var(--rust);
}

.navbar {
   background-color: var(--white);
   background: rgba(255, 255, 255, 0.5);
}


.line {
   width: 90%;
   height: 1px;
   background-color: var(--rust);
   margin-left: 5%;
   box-shadow: 1px 1px 1px grey;
   margin-top: 93px;
   position: fixed;
   z-index: 10;
}

/* NAV BAR */
.navbar-brand {
   color: black;
   margin: -10px 20px;
   font-size: 58px;
}

#page-container {
   margin-top: 100px;
   position: relative;
   min-height: 100vh;
}

#content-wrap {
   padding-bottom: 150px;
   /* Footer height */
}

/* Mobile Styles */
@media only screen and (max-width: 500px) {
   .navbar-brand {
      margin: -10px 5px;
      font-size: 42px;
   }

   #page-container {
      margin-top: 80px;
   }

   .line {
      margin-top: 69px;
   }
}

/* Tablet Styles */
@media only screen and (min-width: 501px) and (max-width: 960px) {
   .navbar-brand {
      margin: -10px 10px;
      font-size: 52px;
   }

   .line {
      margin-top: 84px;
   }
}



/* Footer */

.footer {
   background-color: var(--rust);
   width: 100%;
   height: 150px;
   color: black;
}

.footer-menu {
   text-align: center;
   display: inline-block;
}

.footer-link {
   text-decoration: none;
   color: black;
}

#footer-header {
   font-size: 20px;
}

#source-code-link a {
   color: blue;
}

#footer {
   position: absolute;
   bottom: 0;
   width: 100%;
   height: 150px;
   /* Footer height */
   background-color: var(--rust);
   color: black;

}

/* About */
#profile-pic {
   width: 80%;
   margin: 10%;
   display: inline-block;
}

.about-box {
   font-family: monaco;
}

.box {
   display: inline-block;
   margin: 0 0 3em;
   width: 100%;
}

.word-box {
   padding: 20px;
}


/* Mobile Styles */
@media only screen and (max-width: 600px) {
   .about-box {
      column-count: 1;
      margin: 0px 25px;
   }
}

/* Tablet Styles */
@media only screen and (min-width: 601px) and (max-width: 960px) {
   .about-box {
      column-count: 2;
      column-gap: 2em;
      margin: 0px 5%;
   }
}

/* Desktop Styles */
@media only screen and (min-width: 961px) {
   .about-box {
      column-count: 2;
      column-gap: 3em;
      margin: 0px 15%;
   }
}


/* Create */
.create-box {
   padding: 0px;
}

.toppings-box {
   column-count: 2;
   column-gap: 1em;
}


/* Pizza Product */
#product-pic {
   width: 100%;
   margin-top: 10%;
   display: inline-block;
   box-shadow: 2px 2px 3px grey;
}

.order-button {
   background-color: green;
   border-radius: 15px;
   width: 150px;
   height: 40px;
   box-shadow: 1px 1px 3px grey;
}

.back-button {
   background-color: var(--light-rust);
   width: 100px;
   height: 30px;
   color: black;
   margin-left: 20px;
   border-radius: 10px;
   padding: 5px;
   text-decoration: none;
   text-align: center;
   color: black;
}

.button:hover {
   opacity: 0.8;
}
</style>
