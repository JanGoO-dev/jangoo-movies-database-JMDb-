
<template>

  <nav class="nav-menu-height navbar navbar-expand-lg navbar-dark bg-dark shadow-lg">

    <div class="container">

      <a class="navbar-brand nav-menu-logo px-3 rounded-3 bg-danger" href="#">
        
        <span>J</span><span>M</span><span>Db</span>

      </a>
      
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      
        <span class="navbar-toggler-icon"></span>
      
      </button>
      
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
      
        <ul class="navbar-nav mx-auto mb-2 mb-lg-0 d-flex gap-3">
      
          <li class="nav-item">
      
            <a class="nav-link active" aria-current="page" href="#">Home</a>
      
          </li>
      
          <li class="nav-item">
      
            <a class="nav-link" href="#">Link 1</a>
      
          </li>
      
          <li class="nav-item dropdown">
      
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Dropdown
            </a>
      
            <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
      
              <li><a class="dropdown-item" href="#">Action</a></li>
      
              <li><a class="dropdown-item" href="#">Another action</a></li>
      
              <li><hr class="dropdown-divider"></li>
      
              <li><a class="dropdown-item" href="#">Something else here</a></li>
      
            </ul>
      
          </li>
      
          <li class="nav-item">
      
            <a class="nav-link" href="#">Link 2</a>
      
          </li>
      
        </ul>
      
        <form class="d-flex">
      
          <!-- <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"> -->
      
          <button class="btn btn-danger py-2 px-4" type="submit">Search</button>
      
        </form>
      
      </div>

    </div>

  </nav>

</template>

<script>
  export default {
    name: "NavMenu",
  }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');

.active {
  color: rgb(255, 107, 107) !important;
}

.nav-menu-height {
  height: 75px;
}

@media (max-width: 1000px) {
  .nav-menu-height {
    height: auto;
  }
}

.nav-menu-logo {
  font-family: 'Anton', sans-serif;
  font-size: 1.6em;
  /* background-color: rgb(110, 0, 114) !important; */
}

.nav-menu-logo > span {
  color: rgb(255, 107, 107);
}

.navbar-nav li a,
.navbar-nav li ul li a {
  text-transform: uppercase;
  letter-spacing: 2px;
}
</style>
