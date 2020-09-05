<template>
  <div id="app" class="container-fluid">
    <div class="row">
      <nav id="nav" class="navbar navbar-expand-lg d-flex justify-content-start">
        <!-- Links -->
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link to="/" class="nav-link">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link to="/about" class="nav-link">About</router-link>
          </li>
        </ul>
      </nav>
    </div>
    <div class="row">
      <router-view />
      <router-view name="aside" />
    </div>
  </div>
</template>

<style lang="scss">
@import 'assets/styles/bootstrap/variables';
#app {
  border: 2px solid red;
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background: $white-color;
}

#nav {
  padding: 30px;
  width: 100%;
  background: $primary-color;
}

#nav a {
  font-weight: bold;
  color: $white-color;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
