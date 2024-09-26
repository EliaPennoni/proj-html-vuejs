<script>
export default {
  data() {
    return {};
  },
  props: {
    menuItems: {
      type: Array,
    },
    menuIcons: {
      type: Array,
    },
  },
  methods: {
    showDropdown(index) {
      this.menuItems[index].showDropdown = true;
    },
    hideDropdown(index) {
      this.menuItems[index].showDropdown = false;
    },
  },
};
</script>

<template>
  <nav class="navbar">
    <div class="logo">
      <a href="#">
        <img src="/teach/img/logo-img-01.png" alt="Logo" />
      </a>
    </div>
    <div class="nav-tools">
      <ul class="menu">
        <li
          v-for="(item, index) in menuItems"
          :key="index"
          :class="{ active: item.active }"
          @mouseover="showDropdown(index)"
          @mouseleave="hideDropdown(index)"
        >
          <a :href="item.link"
            >{{ item.label }}
            <div class="drop-down"></div>
          </a>
          <div v-if="item.submenu && item.showDropdown" class="drop-down">
            <ul>
              <li v-for="(subItem, i) in item.submenu" :key="i">
                <a :href="subItem.link">{{ subItem.label }}</a>
              </li>
            </ul>
          </div>
        </li>
      </ul>

      <div class="icons">
        <span v-for="(icon, index) in menuIcons" :key="index" class="icon">
          <a :href="icon.link">
            <i :class="icon.iconClass"></i>
          </a>
        </span>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import "/src/assets/scss/general.scss";
@import "/src/assets/scss/base/variabili.scss";
// Import all of Bootstrap's CSS
.container {
  width: 100%;
  position: relative;
}
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  position: absolute;
  top: 10px;
  z-index: 999;
  padding: 30px;
}
.logo img {
  max-height: 100px;
  max-width: 150px;
}
.nav-tools {
  display: flex;
}

.menu {
  display: flex;
  list-style: none;
}
.menu li {
  position: relative;
}
.menu li a {
  text-decoration: none;
  margin-left: 15px;
  margin-right: 15px;
  font-size: medium;
  font-weight: bold;
  color: $second-back-color;
  text-transform: uppercase;
  position: relative;
}

.menu li a::before {
  content: "\f178";
  font-family: "Font Awesome 5 Free";
  font-weight: 900;
  position: absolute;
  left: -20px;
  top: 50%;
  transform: translateY(-50%);
  opacity: 0;
  transition: opacity 0.5s ease, left 0.5s ease;
}

.menu li a:hover::before {
  opacity: 1;
}

.menu li a:hover {
  color: $primary-color;
}
/* Stile per l'elemento attivo */
.menu li.active a {
  color: $primary-color;
}

.menu li.active a::before {
  opacity: 1;
  left: -20px;
}
.icons span a {
  margin-left: 15px;
  margin-right: 15px;
  color: black;
}
.icons span a:hover {
  color: $primary-color;
}
.drop-down {
  position: absolute;
  top: 100%;
  left: 0;
  min-width: 200px;
  padding: 15px 0;
  opacity: 0;
  height: 0;
  overflow: hidden;
  z-index: 100;
  transition: opacity 0.5s ease, height 0.5s ease;
}

.menu li:hover .drop-down {
  opacity: 1;
  height: auto;
}

/* Dropdown menu items */
.drop-down ul {
  list-style: none;
  padding: 0;
  margin: 0;
  background-color: black;
}

.drop-down li {
  margin: 0;
}

.drop-down ul li a {
  display: block;
  padding: 10px 20px;
  color: white;
  font-size: 14px;
  text-decoration: none;
  font-family: "Libre Baskerville", serif;
  transition: color 0.3s ease;
}

.drop-down ul li a:hover {
  color: white;
}
</style>
