<script>
export default {
  data() {
    return {
      sponsorList: [
        {
          img: "/public/teach/img/h4-clients-img-02.png",
        },
        {
          img: "/public/teach/img/h4-clients-img-04-1.png",
        },
        {
          img: "/public/teach/img/h4-clients-img-06-1.png",
        },
        {
          img: "/public/teach/img/h4-clients-img-08-1.png",
        },
        {
          img: "/public/teach/img/h4-clients-img-10-1.png",
        },
      ],
    };
  },
  methods: {},
};
</script>

<template>
  <div class="background">
    <div class="container">
      <div class="map">
        <img src="/public/teach/img/h1-contact-rev-01.png" alt="" />
        <div class="plus1">
          <img src="/public/teach/img/h1-contact-rev-02.png" alt="" />
          <div class="info">
            <h4>New York</h4>
            <p>Read More</p>
          </div>
        </div>
        <div class="plus2">
          <img src="/public/teach/img/h1-contact-rev-02.png" alt="" />
          <div class="info">
            <h4>Melbourne</h4>
            <p>Read More</p>
          </div>
        </div>
        <div class="plus3">
          <img src="/public/teach/img/h1-contact-rev-02.png" alt="" />
          <div class="info">
            <h4>London</h4>
            <p>Read More</p>
          </div>
        </div>
      </div>
      <div class="ask">
        <h3>Contact us</h3>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
        <div class="input">
          <input type="text" placeholder="Your Name" />
          <input type="email" name="" id="" placeholder="Your E-mail" />
        </div>
        <label for="message"></label>
        <textarea
          id="message"
          name="message"
          rows="4"
          cols="50"
          placeholder="Write a message..."
        ></textarea>

        <button>
          <span>Send</span><span>|</span><i class="fa fa-arrow-right-long"></i>
        </button>
      </div>
    </div>

    <div class="sponsor">
      <div v-for="(sponsor, index) in sponsorList" :key="index" class="card">
        <img :src="sponsor.img" alt="" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "/src/assets/scss/general.scss" as *;

.container {
  width: 90%;
  margin: 0 auto;
  display: flex;
}
.map {
  width: 50%;
  margin-top: 100px;
  position: relative;
}
// .map img {
//   width: 100%;
// }
.ask {
  width: 50%;
  padding: 20px;
  margin-top: 40px;
}
.ask > h3::after {
  content: "";
  display: inline-block;
  width: 5px;
  height: 5px;
  background-color: #ff4612;
  border-radius: 50%;
  margin-left: 3px;
  vertical-align: baseline;
}
.ask p::before {
  content: "";
  display: inline-block;
  width: 60px;
  height: 2px;
  background-color: #ff4612;
  position: absolute;
  bottom: -30px;
  left: 0;
}
.ask h3 {
  font-family: "TuesdayNight", serif;
  font-size: 50px;
  margin-bottom: 5px;
}
.ask p {
  position: relative;
  margin-bottom: 60px;
  font-size: larger;
  color: gray;
  font-family: "TuesdayNight", serif;
}
.input {
  margin-bottom: 20px;
  display: flex;
}
.input input,
textarea {
  border: none;
  border-bottom: 2px solid #ccc;
  outline: none;
  width: 100%;
  padding: 10px;
  margin-bottom: 20px;
  margin-right: 5px;
  font-family: "Libre Baskerville", serif;
  font-size: 16px;
  background-color: transparent;
  transition: border-color 0.3s ease;
}

.input input:focus,
textarea:focus {
  border-bottom: 2px solid #ff4612; /* Colore del bordo al focus */
  background-color: #f8f8f8; /* Leggero cambiamento di sfondo al focus (opzionale) */
}
// button generale----------------------------------------------------------------------------

.ask button span:nth-of-type(1) {
  margin-right: 15px;
}
.ask button span:nth-of-type(2) {
  margin-right: 15px;
  font-size: x-large;
  transition: opacity 0.3s ease, transform 0.3s ease;
  display: inline-block;
}
.ask button:hover span:last-of-type {
  opacity: 0;
  transform: scaley(0);
}
.ask button:hover i {
  transform: translateX(-25px);
  transition: transform 0.3s ease;
}

.ask button {
  background-color: #ff4612;
  color: white;
  border: none;
  padding: 10px 20px;
  font-size: large;
  margin-top: 25px;
  cursor: pointer;
}
// ---------------------------------------------------------------------------------------------

// button {
//   display: block;
//   background-color: #ff4612;
//   color: white;
//   border: none;
//   margin-top: 30px;
//   padding: 15px;
//   display: flex;
//   align-items: center;
// }
// button span {
//   font-size: medium;
//   margin-right: 5px;
// }
.plus1 {
  position: absolute;
  top: 30%;
  left: 150px;
  cursor: pointer;
}
.plus2 {
  position: absolute;
  bottom: 15%;
  right: -10px;
  cursor: pointer;
}
.plus3 {
  position: absolute;
  top: 18%;
  right: 210px;
  cursor: pointer;
}
.plus1 div {
  opacity: 0;
}
.plus2 div {
  opacity: 0;
}
.plus3 div {
  opacity: 0;
}
.plus1 img:hover + .info,
.plus2 img:hover + .info,
.plus3 img:hover + .info {
  opacity: 1;
  visibility: visible;
}
.info {
  background-color: white;
  padding: 10px;
}
.sponsor {
  display: flex;
  justify-content: space-around;
}
.sponsor div {
  margin-top: 60px;
  color: black;
}
</style>
