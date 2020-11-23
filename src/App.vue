<template>
  <div id="app">
    <div class="container">
      <div class="card">
        <div class="card-image mt-5">
          <img alt="Logo" :src="urlLogo" />
        </div>
        <div class="card-content">
          <div class="content has-text-left">
            <GetCertified :src="urlCerts" :email="infoEmail" :chan="infoChan" />
          </div>
        </div>
        <footer class="card-footer">
          <p class="card-footer-item">
            <a :href="urlResults" target="_blank"> View Results </a>
          </p>
          <p class="card-footer-item">
            <a :href="urlSocial" target="_blank"> Social Media </a>
          </p>
        </footer>
      </div>
    </div>
  </div>
</template>

<script>
import GetCertified from "./components/GetCertified";

export default {
  name: "App",
  components: {
    GetCertified,
  },
  data() {
    return {
      infoEmail: process.env.VUE_APP_INFO_EMAIL, // eslint-disable-line
      infoChan: process.env.VUE_APP_INFO_CHANNEL, // eslint-disable-line
      urlLogo: process.env.VUE_APP_URL_LOGO, // eslint-disable-line
      urlCerts: process.env.VUE_APP_URL_CERTS, // eslint-disable-line
      urlResults: process.env.VUE_APP_URL_RESULTS, // eslint-disable-line
      urlSocial: process.env.VUE_APP_URL_SOCIAL, // eslint-disable-line
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 20px;
}
</style>
