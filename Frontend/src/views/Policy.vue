<template>
  <div id="policy">
    <div
      style="overflow:hidden; position:absolute; left:0; top:0; width:50px; height:25px;"
    >
      <div style="margin-top:-290px;"></div>
    </div>

    <p id="start">A short time ago in a browser very, very close&hellip;</p>

    <h1>CPE 223<sub>Friendzone Project</sub></h1>

    <div id="titles">
      <div id="titlecontent">
        <div class="section">
          <img id="fz-logo" src="@/assets/homepage/Group 2@2x.png" />
        </div>

        <p class="center" style="text-transform:uppercase;">
          Terms and Conditions<br />
          Welcome to friendzone!
        </p>

        <p>
          These terms and conditions outline the rules and regulations for the
          use of friend zone's Website, located at friendzone project. We hope
          you giving us an A for this course and hopefully also for the
          nextcourse
        </p>

        <p>
          By accessing this website we assume you accept these terms and
          conditions. Do not continue to use friendzone if you do not agree to
          take all of the terms and conditions stated on this page. The first
          rule is not leave me. Second is not leave me. I will be very mad if
          you dump me. not a trash. I am not a trash. แล้วข้อที่สามก็คือห้ามทิ้ง
          ยันข้อเก้าก็ยังห้ามทิ้ง ไม่ได้แกล้งเนี่ยพูดจริงๆ ฉันไม่ได้แกล้งหลอก
          ฉันไม่ใช่ผีจะมาหลอกเธอได้ไง
        </p>

        <p>
          The following terminology applies to these Terms and Conditions,
          Privacy Statement and Disclaimer Notice and all Agreements: "Client",
          "You" and "Your" refers to you, the person log on this website and
          compliant to the Company’s terms and conditions. "The Company",
          "Ourselves", "We", "Our" and "Us", refers to our Company. "Party",
          "Parties", or "Us", refers to both the Client and ourselves. All terms
          refer to the offer, acceptance and consideration of payment necessary
          to undertake the process of our assistance to the Client in the most
          appropriate manner for the express purpose of meeting the Client’s
          needs in respect of provision of the Company’s stated services, in
          accordance with and subject to, prevailing law of Netherlands. Any use
          of the above terminology or other words in the singular, plural,
          capitalization and/or he/she or they, are taken as interchangeable and
          therefore as referring to same.
        </p>

        <p>
          Cookies We employ the use of cookies. By accessing friendzone, you
          agreed to use cookies in agreement with the friend zone's Privacy
          Policy.
        </p>

        <!-- <div class="section">
          <img id="photo" src="@/assets/profile/harry-200.jpg" />
        </div> -->

        <p>
          Most interactive websites use cookies to let us retrieve the user’s
          details for each visit. Cookies are used by our website to enable the
          functionality of certain areas to make it easier for people visiting
          our website. Some of our affiliate/advertising partners may also use
          cookies.
        </p>

        <p>
          License Unless otherwise stated, friend zone and/or its licensors own
          the intellectual property rights for all material on friendzone. All
          intellectual property rights are reserved. You may access this from
          friendzone for your own personal use subjected to restrictions set in
          these terms and conditions.
        </p>

        <div class="section">
          <button @click="clickAgree()" id="join_button">AGREE</button>
        </div>
      </div>
    </div>
    <iframe
      type="text/html"
      src="https://www.youtube.com/embed/sFvQOc4xS2k?autoplay=1"
      frameborder="0"
      style="visibility:hidden"
      allow="autoplay"
    ></iframe>
  </div>
</template>

<script>
export default {
  methods: {
    clickAgree() {
      this.$router.push("/register");
    }
  }
};
</script>

<style scoped>
* {
  padding: 0;
  margin: 0;
}

body,
html,
#policy {
  width: 100%;
  height: 100vh;
  font-family: "Droid Sans", arial, verdana, sans-serif;
  font-weight: 700;
  color: #ff6;
  background-color: #000;
  background-image: url("https://starwarsblog.starwars.com/wp-content/uploads/2020/04/star-wars-backgrounds-25.jpg");
  background-repeat: no-repeat;
  background-size: cover;
  filter: grayscale;
  overflow: hidden;
}

#fz-logo{
  width:600px;
}

#photo{
  width:100%;
}

p#start {
  position: relative;
  width: 16em;
  font-size: 200%;
  font-weight: 400;
  margin: 20% auto;
  color: #4ee;
  opacity: 0;
  z-index: 1;
  -webkit-animation: intro 2s ease-out;
  -moz-animation: intro 2s ease-out;
  -ms-animation: intro 2s ease-out;
  -o-animation: intro 2s ease-out;
  animation: intro 2s ease-out;
}

@-webkit-keyframes intro {
  0% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@-moz-keyframes intro {
  0% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@-ms-keyframes intro {
  0% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@-o-keyframes intro {
  0% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

@keyframes intro {
  0% {
    opacity: 1;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}

#join_button {
  font-family: "Atten-Round-New";
  font-weight: 600;
  font-size: 1.5em;
  color: #ffffff;
  padding: 8px 90px;
  border: none;
  margin-top: 20px;
  border-radius: 31px;
  background-color: #ff8864;
  -webkit-transform: perspective(1px) translateZ(0);
  transform: perspective(1px) translateZ(0);
  box-shadow: 0 0 1px rgba(0, 0, 0, 0);
  -webkit-transition-duration: 0.3s;
  transition-duration: 0.3s;
  -webkit-transition-property: transform;
  transition-property: transform;
  transition: 0.3s;
  cursor: pointer;
}
#join_button:hover,
#join_button:focus,
#join_button:active {
  -webkit-transform: scale(1.03);
  transform: scale(1.03);
  background-color: #ffbb62;
  color: #ffffff;
  cursor: pointer;
}

h1 {
  position: absolute;
  width: 2.6em;
  left: 50%;
  top: 25%;
  font-size: 10em;
  text-align: center;
  margin-left: -1.3em;
  line-height: 0.8em;
  letter-spacing: -0.05em;
  color: #000;
  text-shadow: -2px -2px 0 #ff6, 2px -2px 0 #ff6, -2px 2px 0 #ff6,
    2px 2px 0 #ff6;
  opacity: 0;
  z-index: 1;
  -webkit-animation: logo 5s ease-out 2.5s;
  -moz-animation: logo 5s ease-out 2.5s;
  -ms-animation: logo 5s ease-out 2.5s;
  -o-animation: logo 5s ease-out 2.5s;
  animation: logo 5s ease-out 2.5s;
}

h1 sub {
  display: block;
  font-size: 0.3em;
  letter-spacing: 0;
  line-height: 0.8em;
}

@-webkit-keyframes logo {
  0% {
    -webkit-transform: scale(1);
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  100% {
    -webkit-transform: scale(0.1);
    opacity: 0;
  }
}

@-moz-keyframes logo {
  0% {
    -moz-transform: scale(1);
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  100% {
    -moz-transform: scale(0.1);
    opacity: 0;
  }
}

@-ms-keyframes logo {
  0% {
    -ms-transform: scale(1);
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  100% {
    -ms-transform: scale(0.1);
    opacity: 0;
  }
}

@-o-keyframes logo {
  0% {
    -o-transform: scale(1);
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  100% {
    -o-transform: scale(0.1);
    opacity: 0;
  }
}

@keyframes logo {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    opacity: 1;
  }
  100% {
    transform: scale(0.1);
    opacity: 0;
  }
}

/* the interesting 3D scrolling stuff */
#titles {
  position: absolute;
  width: 18em;
  height: 50em;
  bottom: 0;
  left: 50%;
  margin-left: -9em;
  font-size: 650%;
  text-align: justify;
  overflow: hidden;
  -webkit-transform-origin: 50% 100%;
  -moz-transform-origin: 50% 100%;
  -ms-transform-origin: 50% 100%;
  -o-transform-origin: 50% 100%;
  transform-origin: 50% 100%;
  -webkit-transform: perspective(300px) rotateX(25deg);
  -moz-transform: perspective(300px) rotateX(25deg);
  -ms-transform: perspective(300px) rotateX(25deg);
  -o-transform: perspective(300px) rotateX(25deg);
  transform: perspective(300px) rotateX(25deg);
}

#titles:after {
  position: absolute;
  content: " ";
  left: 0;
  right: 0;
  top: 0;
  bottom: 60%;
  background-image: -webkit-linear-gradient(
    top,
    rgba(0, 0, 0, 1) 0%,
    transparent 100%
  );
  background-image: -moz-linear-gradient(
    top,
    rgba(0, 0, 0, 1) 0%,
    transparent 100%
  );
  background-image: -ms-linear-gradient(
    top,
    rgba(0, 0, 0, 1) 0%,
    transparent 100%
  );
  background-image: -o-linear-gradient(
    top,
    rgba(0, 0, 0, 1) 0%,
    transparent 100%
  );
  background-image: linear-gradient(top, rgba(0, 0, 0, 1) 0%, transparent 100%);
  pointer-events: none;
}

#titles p {
  text-align: justify;
  margin: 0.8em 0;
}

#titles p.center {
  text-align: center;
}

#titles a {
  color: #ff6;
  text-decoration: underline;
}

#titlecontent {
  position: absolute;
  top: 100%;
  -webkit-animation: scroll 100s linear 4s infinite;
  -moz-animation: scroll 100s linear 4s infinite;
  -ms-animation: scroll 100s linear 4s infinite;
  -o-animation: scroll 100s linear 4s infinite;
  animation: scroll 100s linear 4s infinite;
}

/* animation */
@-webkit-keyframes scroll {
  0% {
    top: 100%;
  }
  100% {
    top: -170%;
  }
}

@-moz-keyframes scroll {
  0% {
    top: 100%;
  }
  100% {
    top: -170%;
  }
}

@-ms-keyframes scroll {
  0% {
    top: 100%;
  }
  100% {
    top: -170%;
  }
}

@-o-keyframes scroll {
  0% {
    top: 100%;
  }
  100% {
    top: -170%;
  }
}

@keyframes scroll {
  0% {
    top: 100%;
  }
  100% {
    top: -170%;
  }
}
@media screen and (max-width: 950px) {
  #titles {
    font-size: 350%;
  }

  #fz-logo{
  width:100%;
}
}

@media screen and (max-width: 690px) {
  p {
    font-size: 1em;
  }

  body,
  html,
  #policy {
    max-width: 100vw;
    max-height: 100vh;
  }

  #titles {
    font-size: 250%;
  }
}
</style>

