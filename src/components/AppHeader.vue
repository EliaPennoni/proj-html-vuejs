<script>
export default {
  data() {
    return {};
  },
};
</script>

<template>
  <header>
    <nav>
      <div class="logo">
        <a href="">
          <img src="/teach/img/logo-img-01.png" alt="" />
        </a>
      </div>
      <div class="list">
        <ul>
          <li><a href="">homes</a></li>
          <li><a href="">pages</a></li>
          <li><a href="">blog</a></li>
          <li><a href="">shop</a></li>
          <li><a href="">events</a></li>
          <li><a href="">elements</a></li>
          <li>
            <a href=""><i class="fa-solid fa-magnifying-glass"></i></a>
          </li>
          <li>
            <a href=""><i class="fa-solid fa-list"></i></a>
          </li>
        </ul>
      </div>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.logo img {
  max-height: 100px;
  max-width: 150px;
}

.list ul {
  display: flex;
  list-style: none;
}
.list ul li {
  position: relative;
}
.list ul li a {
  text-decoration: none;
  margin-left: 15px;
  margin-right: 15px;
  font-size: medium;
  font-weight: bold;
  color: black;
  text-transform: uppercase;
  position: relative;
}

.list ul li a::before {
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

.list ul li a:hover::before {
  opacity: 1;
}

.list ul li a:hover {
  color: #ff4612;
}
</style>
