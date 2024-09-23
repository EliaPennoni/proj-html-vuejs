<script>
export default {
  data() {},
  methods: {},
};
</script>

<template>
  <div class="background">
    <div class="plans">
      <div class="about">
        <h4>About</h4>
        <ul>
          <li>
            <span>
              We created Everlead to effectively become the stepping stone
              towards meeting all your goals & achieving business success.</span
            >
          </li>
        </ul>
        <div class="link">
          <a href=""><i class="fa-brands fa-linkedin"></i></a>
          <a href=""><i class="fa-brands fa-facebook"></i></a>
          <a href=""><i class="fa-brands fa-twitter"></i></a>
        </div>
      </div>
      <div class="twitter">
        <h4>Twitter</h4>
        <ul>
          <li>
            <span>Couldn't connect with Twitter</span>
            <a href=""></a>
          </li>
        </ul>
      </div>
      <div class="important">
        <h4>Important Links</h4>
        <ul>
          <li>
            <a href="">About me</a>
          </li>
          <li>
            <a href="">About you</a>
          </li>
          <li>
            <a href="">Language packs</a>
          </li>
          <li>
            <a href="">Become a coach</a>
          </li>
          <li>
            <a href="">Monthly events</a>
          </li>
        </ul>
      </div>
      <div class="important">
        <h4>Contact Me</h4>
        <ul>
          <li>
            <i class="fa-solid fa-location-dot"></i>
            <a href=""><span>457 BigBlue Street, NY 10013</span></a>
          </li>
          <li>
            <i class="fa-solid fa-phone"></i>
            <a href=""><span>(315) 5512-2579</span></a>
          </li>
          <li>
            <i class="fa-solid fa-envelope"></i>
            <a href=""><span>everlead@qodeinteractive.com</span></a>
          </li>
        </ul>
        <input type="text" name="" id="" placeholder="Your Name" />
      </div>
    </div>
    <footer>
      <span
        ><i class="fa-solid fa-copyright"></i>2019 Qode Interactive, All Right
        Reserved</span
      >
    </footer>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;

.background {
  background-color: black;
}
.plans {
  display: flex;
  justify-content: space-evenly;
  color: lightgray;
}
.plans > div {
  width: 280px;
  padding: 20px;
}
.plans div ul {
  list-style: none;
}
.plans div ul li a {
  text-decoration: none;
  color: white;
  font-size: small;
  margin-left: 5px;
}
.plans div ul li {
  margin-bottom: 10px;
}
.plans div ul li i {
  color: #ff4612;
}
.plans h4 {
  margin-bottom: 20px;
  color: white;
  font-size: 20px;
  font-family: "TuesdayNight", serif;
  position: relative;
}
.plans h4::after {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: -10px;
  right: 75%;
}
.link {
  display: flex;
}
.link a {
  text-decoration: none;
}
.link i {
  margin-top: 10px;
  margin-right: 15px;
  background-color: white;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 20px;
  color: black;
}
.link i:hover {
  color: #ff4612;
}
input {
  margin-top: 30px;
  border-top: none;
  border-right: none;
  border-left: none;
  border-bottom: 2px solid gray;
  background-color: black;
  color: lightgray;
  padding: 10px 5px;
  width: 100%;
  font-size: 16px;
  font-family: "Libre Baskerville", serif;
  outline: none;
  transition: border-color 0.3s ease;
}

input::placeholder {
  color: gray;
}

input:focus {
  border-bottom: 2px solid #ff4612;
  background-color: #1e1e1e;
  color: lightgray;
}
.important ul li a {
  color: lightgray;
}
.important ul li a:hover {
  color: white;
}
footer {
  background-color: #ff4612;
  color: white;
  font-size: small;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
  width: 100%;
}
</style>
