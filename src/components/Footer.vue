<template>
  <footer>
    <div class="container-fluid">
      <div class="col-md-12">
        <p>
          Copyright &copy;
          {{ new Date().getFullYear() }}
          Rodrigo Costas | Desarrollado por
          <a
            href="https://www.behance.net/martindeangelis"
            target="_blank"
            rel="noreferer noopener"
            >Martín De Angelis</a
          >
        </p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
footer {
  position: fixed;
  bottom: 0;
  right: 0;
  width: 85%;
  color: white;
  text-align: center;
  font-family: "Open sans", sans-serif;
  font-size: 0.75rem;
  width: 100%;
  background-color: #313131;
}
footer a {
  color: white;
}
footer a:hover {
  color: rgb(219, 219, 219);
  text-decoration: none;
}
footer p {
  text-align: center;
  color: #fff;
  font-weight: 200;
  font-size: 13px;
  text-transform: uppercase;
  padding-top: 33px;
  letter-spacing: 0.5px;
}

footer a {
  color: #aaa;
  text-decoration: none;
}

footer a:hover {
  text-decoration: none;
  color: #aaa;
}
</style>
