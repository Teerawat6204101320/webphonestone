<template>
  <div class="hello">
    <!-- slide Start -->
    <div class="slidershow middle">
      <div class="sliders">
        <input type="radio" name="r" id="r1" checked />
        <input type="radio" name="r" id="r2" />
        <input type="radio" name="r" id="r3" />
        <div class="slide s1">
          <img
            src="https://scontent.fbkk13-2.fna.fbcdn.net/v/t1.0-9/157431671_2900951636807190_7979814492035256168_o.jpg?_nc_cat=107&ccb=1-3&_nc_sid=730e14&_nc_eui2=AeFRBHK63qgP00uBax3vJkTvhnv46BXJKSqGe_joFckpKiC987-8Ia6aXWdomBXMW0-f6FmFNAznIDTcXWW_-fFu&_nc_ohc=DdHkMq_Ayq4AX-1mQeD&_nc_oc=AQk9hsI56ZpkfA-SX9w6RE65VSGpUEKm1UzpM1P05fH8OED3Ya8Bp43SJ0m9ZKWgHcg&_nc_ht=scontent.fbkk13-2.fna&oh=82cd7ef8da4f5d1267b1f3a89e2e170a&oe=606A2491"
            alt=""
          />
        </div>
        <div class="slide">
          <img
            src="https://scontent.fbkk12-1.fna.fbcdn.net/v/t1.0-9/157742524_2900994010136286_8551377207479900448_o.jpg?_nc_cat=101&ccb=1-3&_nc_sid=730e14&_nc_eui2=AeF3W8fKidh4pdAIvdWRECR2YQhuBGRbO5ZhCG4EZFs7lipKna7YuO_eKJu6XpKb2FzlEdUd5jvw-jxCOMb-gorD&_nc_ohc=3rMY-SEILHIAX9RjV7E&_nc_ht=scontent.fbkk12-1.fna&oh=8fd98cc5e74d19aacefefb07500e6feb&oe=606B98F1"
            alt=""
          />
        </div>
        <div class="slide">
          <img
            src="https://scontent.fbkk12-1.fna.fbcdn.net/v/t1.0-9/157222503_2900994203469600_2501216965730954207_o.jpg?_nc_cat=101&ccb=1-3&_nc_sid=730e14&_nc_eui2=AeEvwhf6QanV3LcHyqqA5X7_insvnTfzCMmKey-dN_MIyYV7U0-xKlT1V2vJy9AH7nsLZp_ijV18O7YuwYwAXjNm&_nc_ohc=wsUSIGH-ndQAX-C9LxK&_nc_ht=scontent.fbkk12-1.fna&oh=38f002571a30b3e7fe8aed8f09b0cc9e&oe=606CFB64"
            alt=""
          />
        </div>
      </div>
      <div class="navigation">
        <label for="r1" class="bar"></label>
        <label for="r2" class="bar"></label>
        <label for="r3" class="bar"></label>
      </div>
    </div>

    <!-- Samsung product start -->
    <div class="container">
      <div class="product" v-for="(items, index) in todoss" :key="index">
        <div class="product-card">
          <h2 class="name">{{ items.name }}</h2>
          <h3 class="version">{{ items.version }}</h3>
          <span class="price">฿ {{ items.price }}</span>
          <a class="popup-btn">Quick View</a>
          <img class="product-img" :src="items.img" alt="" />
        </div>
        <div class="popup-view">
          <div class="popup-card">
            <a><i class="fa fa-times close-btn"></i></a>
            <div class="product-img">
              <img :src="items.img" alt="" />
            </div>
            <div class="info">
              <h2>
                {{ items.name }}<br /><span>{{ items.version }}</span>
              </h2>
              <p>{{ items.about1 }}</p>
              <p>{{ items.about2 }}</p>
              <p>{{ items.about3 }}</p>
              <p>{{ items.about4 }}</p>
              <p>{{ items.about5 }}</p>
              <span class="price">฿ {{ items.price }}</span>
              <a href="" class="add-cart-btn">Add to Cart</a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import { mapGetters } from "vuex";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  computed: {
    ...mapGetters(["todoss"]),
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Kanit:wght@100&family=Poppins:wght@100&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100&display=swap");
.hello {
  margin: 0;
  padding: 0;
  display: flex;
  font-family: "Poppins", sans-serif;
}
.slidershow {
  width: 1200px;
  height: 400px;
  overflow: hidden;
}
.middle {
  position: absolute;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.navigation {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translate(-50%);
  display: flex;
}
.bar {
  width: 50px;
  height: 10px;
  border: 2px solid white;
  margin: 6px;
  cursor: pointer;
  transition: 0.4s;
}
.bar:hover {
  background: white;
}
input[name="r"] {
  position: absolute;
  visibility: hidden;
}
.sliders {
  width: 500%;
  height: 100%;
  display: flex;
}
.slide {
  width: 20%;
  transition: 0.6s;
}
.slide img {
  width: 100%;
  height: 100%;
}
#r1:checked ~ .s1 {
  margin-left: 0;
}
#r2:checked ~ .s1 {
  margin-left: -20%;
}
#r3:checked ~ .s1 {
  margin-left: -40%;
}
.container {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100vh;
  margin-top: 26%;
}
.container h1 {
  text-align: center;
  color: red;
  font-weight: bold;
}
.product .product-card {
  z-index: 1;
  background: #1d212b;
  position: relative;
  width: 300px;
  height: 450px;
  margin: 40px;
  border-radius: 10px;
}
.product .product-card:before {
  content: "";
  background: rgba(255, 255, 255, 0.1);
  position: absolute;
  display: block;
  top: 0;
  left: 0;
  width: 50%;
  height: 100%;
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
}
.product .product-card .product-img {
  z-index: 2;
  position: absolute;
  max-width: 250px;
  height: 250px;
  top: 35%;
  left: 50%;
  transform: translate(-50%, -50%);
  border-radius: 5px;
}
.product .product-card .name {
  z-index: 3;
  color: white;
  position: absolute;
  width: 100%;
  text-align: center;
  bottom: 110px;
  letter-spacing: 1px;
  text-transform: uppercase;
}
.product .product-card .version {
  z-index: 3;
  color: white;
  position: absolute;
  width: 100%;
  text-align: center;
  bottom: 85px;
  letter-spacing: 1px;
}
.product .product-card .price {
  z-index: 3;
  color: white;
  position: absolute;
  width: 100%;
  text-align: center;
  bottom: 60px;
  font-size: 15px;
  font-weight: 600;
}
.product .product-card .popup-btn {
  z-index: 3;
  color: white;
  background: #555;
  position: absolute;
  bottom: 10px;
  left: 50%;
  transform: translate(-50%);
  font-size: 14px;
  text-transform: uppercase;
  text-decoration: none;
  letter-spacing: 1px;
  padding: 10px 15px;
  border-radius: 20px;
  cursor: pointer;
  font-weight: 600;
}
.product .popup-view {
  z-index: 3;
  background: rgba(255, 255, 255, 0.5);
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  visibility: hidden;
  transition: 0.5s;
}
.product .popup-view.active {
  opacity: 1;
  visibility: visible;
}
.product .popup-card {
  position: relative;
  display: flex;
  width: 800px;
  height: 500px;
  margin: 20px;
}
.product .popup-card .product-img {
  z-index: 3;
  background: #1d212b;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 45%;
  height: 90%;
  transform: translateY(25px);
  border-top-left-radius: 10px;
  border-bottom-left-radius: 10px;
}
.product .popup-card .product-img img {
  z-index: 3;
  position: relative;
  width: 270px;
  left: 0px;
  border-radius: 5px;
}
.product .popup-card .info {
  z-index: 3;
  background: rgb(255, 167, 4);
  display: flex;
  flex-direction: column;
  width: 55%;
  height: 100%;
  box-sizing: border-box;
  padding: 40px;
  border-radius: 10px;
}
.product .popup-card .close-btn {
  color: #555;
  z-index: 4;
  position: absolute;
  right: 0;
  font-size: 20px;
  margin: 20px;
  cursor: pointer;
}
.product .popup-card .info h2 {
  font-size: 30px;
  line-height: 20px;
  margin: 10px;
  text-transform: uppercase;
}
.product .popup-card .info h2 span {
  font-size: 15px;
  text-transform: none;
  letter-spacing: 2px;
}
.product .popup-card .info p {
  font-size: 12px;
  margin: 3px;
  color: black;
  font-weight: bold;
  font-family: "Kanit", sans-serif;
}
.product .popup-card .info .price {
  font-size: 45px;
  font-weight: bold;
  margin: 10px;
}
.product .popup-card .info .add-cart-btn {
  color: #fff;
  background: #009dd2;
  font-size: 16px;
  font-weight: bold;
  text-align: center;
  text-decoration: none;
  text-transform: uppercase;
  margin: 10px;
  padding: 10px 50px;
  border-radius: 20px;
}
@media screen and (max-width: 2560px) {
  .slidershow {
    width: 900px;
  }
  .middle {
    top: 45%;
  }
}
@media screen and (max-width: 1088px) {
  .slidershow {
    width: 900px;
  }
  .middle {
    top: 45%;
  }
}
@media screen and (max-width: 966px) {
  .slidershow {
    width: 700px;
    height: 300px;
  }
  .middle {
    top: 37%;
  }
}
@media screen and (max-width: 770px) {
  .slidershow {
    width: 500px;
    height: 230px;
  }
  .middle {
    top: 32%;
  }
  .product .popup-card {
    flex-direction: column;
    width: 550px;
    height: auto;
  }
  .product .popup-card .product-img {
    z-index: 4;
    width: 100%;
    height: 300px;
    transform: translateY(0);
    border-bottom-left-radius: 0px;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
  }
  .product .popup-card .product-img img {
    left: inherit;
    max-width: 100%;
  }
  .product .popup-card .info {
    width: 100%;
    height: auto;
    padding: 20px;
    border-top-left-radius: 0px;
    border-top-right-radius: 0px;
  }
  .product .popup-card .info h2 {
    margin: 20px 5px 5px 5px;
    font-size: 25px;
  }
  .product .popup-card .info h2 span {
    font-size: 10px;
  }
  .product .popup-card .info p {
    margin: 5px;
    font-size: 13px;
  }
  .product .popup-card .info .price {
    margin: 5px;
    font-size: 25px;
  }
  .product .popup-card .info .add-cart-btn {
    margin: 5px auto;
    padding: 5px 40px;
    font-size: 14px;
  }
  .product .popup-card .close-btn {
    z-index: 5;
    color: white;
  }
}
@media screen and (max-width: 500px) {
  .slidershow {
    width: 350px;
    height: 150px;
  }
  .middle {
    top: 25%;
  }
  .bar {
    width: 25px;
    height: 10px;
  }
}
@media screen and (max-width: 322px) {
  .slidershow {
    width: 300px;
    height: 150px;
  }
  .middle {
    transform: translate(-37%, -50%);
  }
}
</style>
