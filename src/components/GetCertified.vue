<template>
  <div class="getCertified">
    <section class="columns form" v-show="!isDownloading">
      <div class="column">
        <div class="preview box" style="display: inline-block">
          <img :src="previewUrl" />
        </div>
      </div>
      <div class="column is-three-quarters">
        <b-field label="First Name">
          <b-input v-model="first_name"></b-input>
        </b-field>

        <b-field label="Last Name">
          <b-input v-model="last_name"></b-input>
        </b-field>

        <div class="field">
          <b-checkbox v-model="honestyPolicy">
            <b
              >I took part in the hackathon and attest to my honest
              contribution</b
            >
            in agreement with the
            <a href="https://hackcodeofconduct.org/" target="_blank"
              >Hack Code of Conduct</a
            >
            during the event, knowing that the organizers fully reserve the right
            to withdraw their recognition of my participation in case of
            misconduct.
          </b-checkbox>
        </div>

        <div class="field has-text-centered m-5">
          <button
            class="button is-primary"
            :disabled="!honestyPolicy"
            @click="getCertified"
          >
            Get certificate
          </button>
        </div>
      </div>
    </section>

    <section class="confirm m-5" v-show="isDownloading">
      <h2>
        &#x1F389; Woo hoo!
      </h2>
      <p>Your certificate is ready:</p>
      <a :href="downloadUrl" download>
        <button class="button is-success is-large">&blacktriangledown; Download PDF</button></a>
    </section>

    <section class="confirm" v-show="isErrored">
      <b-notification type="is-warning" :closable="false">
        There was an error. Please try correcting the spelling of your first or
        last name, which must <u>Be Capitalized</u> to match your answers in the
        registration form.
        Contact the organizing team if you continue having an issue:
        <ul>
          <li v-if="chan"><a :href="chan" target="_blank">support channel</a></li>
          <li v-if="mailTo"><a :href="mailTo">send e-mail</a></li>
        </ul>
      </b-notification>
    </section>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "HelloWorld",
  props: {
    src: String,
    chan: String,
    email: String
  },
  data() {
    return {
      first_name: "",
      last_name: "",
      honestyPolicy: false,
      isDownloading: false,
      downloadUrl: null,
      previewUrl: null,
      isErrored: false,
      mailTo: null,
    };
  },
  methods: {
    getCertified: function () {
      // build download link
      this.downloadUrl = [this.first_name.trim(), " ", this.last_name.trim(), ".pdf"].join("");
      this.downloadUrl = [this.src, this.downloadUrl].join("/");
      // check if the link resolves
      this.isErrored = false;
      axios
        .get(this.downloadUrl)
        .then(this.processDownload)
        .catch((e) => {
          console.warn(e);
          // try without spaces
          axios
            .get(this.downloadUrl.replace(" ", ""))
            .then(this.processDownload)
            .catch((e) => {
              console.warn(e);
              // show error message
              this.isErrored = true;
            });
        });
    },
    processDownload: function () {
      let confetti = this.$confetti;
      // replace form with confirmation
      this.isDownloading = true;
      this.isErrored = false;
      confetti.start({
        particlesPerFrame: 0.5,
      });
      setTimeout(function() {
        confetti.stop();
      }, 5000)
    }
  },
  mounted() {
    this.previewUrl = this.src + "/preview.png";
    this.mailTo = this.email ? "mailto:" + this.email + "?subject=Certificate" : '';
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.preview img {
  width: 200px;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
