<template>
  <nav class="navbar navbar-expand-lg navbar-light p-0">
    <div class="container">
      <a class="navbar-brand logo" href="/"
        ><img src="../assets/images/icons/logo.png" alt="logo"
      /></a>
      <div
        class="collapse collapse-fontsize navbar-collapse"
        id="navbarSupportedContent"
      >
        <ul class="navbar-nav me-auto mb-lg-0">
          <li
            class="nav-item menu-link"
            v-for="(menu, index) in headerMenuList"
            :key="index"
            :class="isActiveClassHadnler(menu.path)"
          >
            <router-link
              class="nav-link"
              aria-current="page"
              :to="menu.path"
              exact
            >
              {{ menu.name }}
            </router-link>
          </li>
        </ul>
        <div class="icons">
          <a href="https://www.facebook.com/" target="_blank"
            ><img src="../assets/images/icons/f.png" alt=""
          /></a>
          <a href="https://www.pinterest.ru/" target="_blank"
            ><img src="../assets/images/icons/p.png" alt=""
          /></a>
          <a href="https://www.instagram.com/" target="_blank"
            ><img src="../assets/images/icons/insta.png" alt=""
          /></a>
          <a href="https://myaccount.google.com/" target="_blank"
            ><img src="../assets/images/icons/g+.png" alt=""
          /></a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import { menuList } from "../constants/menuLinks";
export default {
  name: "Header",
  data() {
    return {
      headerMenuList: menuList,
    };
  },
  methods: {
    isActiveClassHadnler(link) {
      return link === this.$route.path ? "header__isActive" : "";
    },
  },
};
</script>

<style >
@import "../assets/layouts/index.css";
.navbar {
  height: 90px;
}
.navbar .nav-link {
  white-space: nowrap;
}
.header__isActive {
  background: #f2f2f2;
}
.navbar-nav {
  height: 90px;
}
.logo {
  padding-right: 180px;
}
.collapse-fontsize {
  font-size: 18px;
}
.menu-link {
  padding: 25px 30px;
}
.menu-link:hover {
  background: #f2f2f2;
}
.icons {
  width: 180px;
}
.icons a {
  width: 30px;
  height: 30px;
  text-align: center;
  border: 1px solid #f2f2f2;
  border-radius: 50%;
  margin-right: 10px;
  display: inline-block;
}
</style>
