<template>
    <footer class="footer">
      <div class="container">
        <div class="row">
          <div class="col-12 text-center">
            <p class="text-white">Síguenos en:</p>
            <ul class="social-media">
              <li><a href="#" target="_blank"><i class="fab fa-facebook-f"></i></a></li>
              <li><a href="#" target="_blank"><i class="fab fa-twitter"></i></a></li>
              <li><a href="#" target="_blank"><i class="fab fa-instagram"></i></a></li>
            </ul>
          </div>
        </div>
        <div class="row">
          <div class="col-12 text-center">
            <p class="text-white">© 2023 Nombre de la Tienda. Todos los derechos reservados.</p>
          </div>
        </div>
      </div>
    </footer>
  </template>

<script>
export default {
name:"FoterComponent",
};
</script>
  
  <style>
  .footer {
    background-color: #000;
    padding: 20px 0;
  }
  
  .text-white {
    color: #fff;
    font-size: 14px;
  }
  
  .social-media {
    list-style: none;
    padding: 0;
    margin-top: 10px;
  }
  
  .social-media li {
    display: inline-block;
    margin-right: 10px;
  }
  
  .social-media li a {
    color: #fff;
    font-size: 18px;
  }
  
  .social-media li a:hover {
    color: #ccc;
  }
  </style>
  