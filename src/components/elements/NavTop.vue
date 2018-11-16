<template>
    <b-navbar toggleable="md" type="dark" variant="dark">

        <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

        <b-navbar-brand href="#">NavBar</b-navbar-brand>

        <b-collapse is-nav id="nav_collapse">
            <b-navbar-nav>
                <b-nav-item :to="{ path: item.path }" v-for="item in items">{{item.name}}</b-nav-item>
            </b-navbar-nav>
        </b-collapse>
    </b-navbar>
</template>
<script>
  export default {
    name: 'nav-top',
    data() {
      return {
        items: []
      }
    },
    created() {
      this.$router.options.routes.forEach(route => {
        this.items.push({
          name: route.name
          , path: route.path
        })
      })
    }

  }
</script>