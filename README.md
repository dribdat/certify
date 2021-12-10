# certify-participant

This is a simple form which redirects to a download link. Asks participants to attest to having followed the Hack of Conduct.

It is a dead-simple solution to distributing certificates to event participants, which could be built upon later.

Created with Vue.js, Buefy, Axios and CodeSandbox

![text383](https://user-images.githubusercontent.com/31819/145542974-dfe06dac-ac04-4a48-946a-55a2f6c8acc5.png)


## Deployment

To install, set the following environment variables:

- `VUE_APP_URL_CERTS` - the public folder where certificate files are kept.
  - Currently only files formatted as `FirstnameLastname.pdf` are supported.
  - Note: a **preview.png** is expected to also be at this location.
- `VUE_APP_URL_LOGO` - logo of the event (PNG, JPG)
- `VUE_APP_URL_SOCIAL` - social media link (hashtag or account)
- `VUE_APP_URL_RESULTS` - location where the results of the hackathon can be viewed
- `VUE_APP_INFO_EMAIL` - an e-mail address for further information.
- `VUE_APP_INFO_CHANNEL` - the URL of a chat channel for further information.

## License

MIT - see [LICENSE](LICENSE)
