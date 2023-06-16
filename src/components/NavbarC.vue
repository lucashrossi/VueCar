<template>
  <div>
    <b-navbar class="navbar navbar-expand-lg fixed-top navbar-scroll">
      <div class="container-fluid">
        <b-navbar-brand href="#">Programa</b-navbar-brand>

        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

        <b-collapse id="nav-collapse" is-nav>
         

          <b-navbar-nav class="">
          

            <b-dropdown right no-caret>
              <template #button-content>
                <b-icon icon="person-circle" class="nav-icon"></b-icon>
              </template>
              <b-dropdown-item href="#">Perfil</b-dropdown-item>
              <b-dropdown-item href="#">Sesion</b-dropdown-item>
            </b-dropdown>

          

            <b-button v-b-toggle.sidebar-cart class="nav-btn">
              <b-icon icon="cart" class="nav-icon"></b-icon>
            </b-button>
          </b-navbar-nav>
        </b-collapse>
      </div>
    </b-navbar>
  </div>
</template>

<script>
export default {
  name: "NavbarC",
  components: {},
  props: {},
};
</script>

<style scoped>
.navbar {
  width: 100%;
  min-width: 20rem;
  min-height: 4rem;
  z-index: 9;
  color: rgb(220, 180, 20);
  background: rgba(23, 7, 94, 0.676);
  backdrop-filter: blur(5px);
  box-shadow: 0 4px 8px rgba(163, 135, 135, 0.1);
}




.nav-icon {
  color: rgb(255, 255, 255);
}

button {
  border-radius: 50%;
  margin-left: 0.5rem;
  background-color: rgb(21, 123, 25);
  border-color: rgb(49, 106, 65);
  padding: 13px;
}


</style>
