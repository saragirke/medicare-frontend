<template> 
    <div class="header">
        <div class="menu-bar">
    
        <nav class="navbar navbar-expand-lg navbar-light">
        <img src="../img/testlogo.png" alt="logo">
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="" role="button" ><i class="fa fa-bars" aria-hidden="true" style="color:#e6e6ff"></i></span>
    </button>
        <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto">
          <li class="nav-item">
            <RouterLink class="nav-link" to="/">Startsida</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink class="nav-link" to="/inventory">Lager</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink class="nav-link" to="/accounts">Användarkonton</RouterLink>
          </li>
        </ul>
      </div>
    </nav>
    
        </div></div>
    
       <!-- <font-awesome-icon icon="fa-solid fa-bars" /> -->
    
    </template>
    
    <script>
    import { RouterLink } from 'vue-router'
    export default {
        components: {
            RouterLink
        }
    }
    </script>
    
    <style scoped>
    .menu-bar {
        background-image: linear-gradient(-90deg, rgb(72, 186, 164), #0f5d9c); /* #32a871 */
    }
    
    .nav-link {
        font-size: 20px;
        margin: 5px;
        color: white;
    }
    
    .navbar-nav {
        text-align: right;
        margin-right: 20px;
    }
    
    .menu-bar .navbar-toggler {
        padding-right: 20px;
        outline: none!important;
        border: none!important;
    }
    
    .navbar .fa {
        color: white!important;
        font-size: 26px;
    }
    
    .nav-link:hover {
        font-weight: 600;
        border-bottom: 1px solid white;
    }
    
    .navbar-toggler-icon {
        color: white!important;;
    }
    
    @media only screen and (max-width: 990px) {
        .nav-link:hover {
            border-bottom: none!important;
        }
    }
    </style>