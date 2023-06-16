<template>
    <nav class="navbar navbar-dark bg-primary">
      <div class="container">
        <div class="navbar-brand">PandaLandia</div>
        <div class="navbar-icons">
          <a href="/carrito" class="nav-link">
            <i class="bi bi-cart3"></i>
            Carrito
          </a>
          <a href="../components/LoginComponent.vue" class="nav-link">
            <i class="bi bi-person"></i>
            Iniciar sesión
          </a>
        </div>
      </div>
    </nav>
  </template>

<script>
export default {
name:"NavbarComponent",
};
</script>

<style scoped>
.navbar {
  padding: 10px 20px;
}

.navbar-brand {
  font-size: 24px;
  font-weight: bold;
}

.navbar-icons {
  display: flex;
  align-items: center;
}

.navbar-icons .nav-link {
  color: #fff;
  margin-left: 10px;
  text-decoration: none;
  display: flex;
  align-items: center;
}

.navbar-icons .nav-link i {
  margin-right: 5px;
}
</style>