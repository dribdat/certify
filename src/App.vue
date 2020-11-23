<template>
  <div id="app">
    <div class="container">
      <div class="card">
        <div class="card-image mt-5">
          <img
            alt="Logo"
            src="https://make.opendata.ch/files/2013/01/Make.OpenData.ch-Logo1.png"
          />
        </div>
        <div class="card-content">
          <div class="content has-text-left">
            <GetCertified
              baseUrl="https://bucketeer-e34189e0-4cb3-496d-a72e-2dcf17cab858.s3-eu-west-1.amazonaws.com/public/certs/oedh2020"
            />
          </div>
        </div>
        <footer class="card-footer">
          <p class="card-footer-item">
            <span>
              Follow on
              <a href="https://twitter.com/opendatach" target="_blank"
                >Twitter</a
              >
            </span>
          </p>
          <p class="card-footer-item">
            <span>
              Like on
              <a href="https://facebook.com/opendatach" target="_blank"
                >Facebook</a
              >
            </span>
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
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.card {
  max-width: 600px;
}
</style>
