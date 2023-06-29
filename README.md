# certify

This is a small web application with a form which redirects to a download link. Asks participants to attest to having followed the [Hack Code of Conduct](https://hackcodeofconduct.org/). You can easily modify the [content here](https://github.com/loleg/certify/blob/main/src/components/GetCertified.vue#L18).

Use this for a quick, simple solution to distributing certificates to event participants. We usually generate the certificates using an Inkscape template, some data in a CSV file, and [this Python script](https://gist.github.com/loleg/76a2cd97f4acf07ce70663c47a3dd641).

A more sophisticated process, connected to an actual API, is under development at [proxeus-node-dribdat](https://github.com/dribdat/proxeus-node-dribdat).

Created with Vue.js, Buefy, Axios and CodeSandbox

![text383](https://user-images.githubusercontent.com/31819/145542974-dfe06dac-ac04-4a48-946a-55a2f6c8acc5.png)
_An example certificate from an [Opendata.ch](https://opendata.ch) Hackday_

## Deployment

To install, set the following environment variables:

- `VUE_APP_URL_CERTS` - the public folder where certificate files are kept.
  - Currently only files formatted as `FirstnameLastname.pdf` are supported.
  - Note: a **preview.png** is expected to also be at this location.
  - No trailing slash.
- `VUE_APP_URL_LOGO` - logo of the event (PNG, JPG)
- `VUE_APP_URL_SOCIAL` - social media link (hashtag or account)
- `VUE_APP_URL_RESULTS` - location where the results of the hackathon can be viewed
- `VUE_APP_INFO_EMAIL` - an e-mail address for further information.
- `VUE_APP_INFO_CHANNEL` - the URL of a chat channel for further information.

## License

MIT - see [LICENSE](LICENSE)
