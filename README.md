# certify-participant

This is a simple form which redirects to a download link. Asks participants to attest to having followed the Hack of Conduct.

It is a dead-simple solution to distributing certificates to event participants, which could be built upon later.

Created with Vue.js, Buefy, Axios and CodeSandbox

## Deployment

To install, set the following environment variables:

- `URL_CERTS` - the public folder where certificate files are kept.
  - Currently only files formatted as `FirstnameLastname.pdf` are supported.
  - Note: a **preview.png** is expected to also be at this location.
- `URL_LOGO` - logo of the event (PNG, JPG)
- `URL_SOCIAL` - social media link (hashtag or account)
- `URL_RESULTS` - location where the results of the hackathon can be viewed
- `INFO_EMAIL` - an e-mail address for further information.
- `INFO_CHANNEL` - the URL of a chat channel for further information.

## License

MIT - see [LICENSE](LICENSE)