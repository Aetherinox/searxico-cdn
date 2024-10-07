<div align="center">
<h6>Favicon CDN for SearXNG</h6>
<h2>☁️ Searxico - Favicon Grabber CDN ☁️</h1>

<br />

<p>

Used in combination with the [Searxico Favicon Worker](https://github.com/Aetherinox/searxico-worker) to store favicons for various websites.

</p>

<br />

<img src="https://raw.githubusercontent.com/Aetherinox/searxico-worker/refs/heads/main/docs/img/banner.png" height="230">

<br />
<br />

</div>

<div align="center">

<!-- prettier-ignore-start -->
[![Version][github-version-img]][github-version-uri]
[![Downloads][github-downloads-img]][github-downloads-uri]
[![Build Status][github-build-img]][github-build-uri]
[![Size][github-size-img]][github-size-img]
[![Last Commit][github-commit-img]][github-commit-img]
[![Contributors][contribs-all-img]](#contributors-)

[![Built with Material for MkDocs](https://img.shields.io/badge/Powered_by_Material_for_MkDocs-526CFE?style=for-the-badge&logo=MaterialForMkDocs&logoColor=white)](https://aetherinox.github.io/traefik-api-token-middleware/)
<!-- prettier-ignore-end -->

</div>

<br />

---

<br />

- [About](#about)
- [Contributing](#contributing)
- [Self-Hosted Ports](#self-hosted-ports)
- [Trademark Disclaimer](#trademark-disclaimer)
- [Contributors ✨](#contributors-)

<br />

---

<br />

## About

This repo serves as a content delivery network to override certain website favicons that are either difficult to see, or may implement measures which disallow grabbing the favicon from their website. It is to be used in combination with the self-hosted [Searxico Favicon Worker](https://github.com/Aetherinox/searxico-worker).

<br />

If a user attempts to locate a favicon for a particular website, this repository will be the first place that is checked. It will attempt to find an icon here and return it. If an icon does not exist for a particular domain in this repository; the favicon worker will then proceed forward with checking the domain itself for a current favicon.

<br />

If you wish to host your own version of this repository to store icons, fork this repository, add your own icons, and then push a new repository from your Github account.

<br />

After you have created the new repository, open the source code within `/src/index.js` from the [Worker Repository](https://github.com/Aetherinox/searxico-worker) and change the following line to your new repository URL:

```js
const serviceBackup = 'https://raw.githubusercontent.com/Aetherinox/searxico-cdn/main';
```

<br />

A working demo can be tried at the below address:
```
https://searxico.aetherinox.workers.dev/get/{DOMAIN}/{ICON_SIZE}
https://searxico.aetherinox.workers.dev/get/reddit.com/64
```

<br />

---

<br />

## Contributing

If you have attempted to grab an icon for a certain website that is either difficult to see, or will not properly capture; you may submit an override icon to this repo. However, ensure the following:

<br />

- Submissions MUST be in `.ico` icon format
- Must include the following sizes:
  - 64 x 64
  - 48 x 48
  - 32 x 32
  - 24 x 24
  - 20 x 20
  - 16 x 16
- All sizes need to be combined into a single `.ico` file
- Each icon should not exceed `100kb`
- Icon should be placed in a parent folder which starts with the first letter of the service
  - Ex: `/r/reddit.com.ico` for Reddit
  - If you are providing a favicon for a subdomain, the folder name should start with the first letter of the subdomain, not the base domain.
    - Ex: `/f/forum.libriv.ox.org.ico`
  - Domains with dashes should be labeled with the same character.
    - Ex: `/r/random-website.com.ico`
  - Anything after the TLD _(top-level domain : .com, .org, .net, etc.)_ is ignored.
    - Ex: https://subdomain.my-domain-example.com/example/page/file.html should have a favicon in `/s/subdomain.my-domain-example.com.ico`
  
<br />

If you need an easy solution for converting icons to `.ico` with the proper sizes, you can install:
- [Simple File Icon Maker](https://github.com/TheJoeFin/Simple-Icon-File-Maker)

<br />

<p align="center"><img style="width: 80%;text-align: center;" src="https://raw.githubusercontent.com/Aetherinox/searxico-worker/refs/heads/main/docs/img/icon-convert/1.png"></p>

<br />

<br />

---

<br />

## Self-Hosted Ports
This repo supports fetching icons for locally hosted web-apps. However, keep in mind that some applications conflict and may share the same port. 

In order to fetch the icon, you will need to change conflicting web-app ports to the same port specified below:

| App | Default Port | Repo Port |
| --- | --- | --- |
| [Duplicacy](https://github.com/gilbertchen/duplicacy) | 3875 | `3875` |
| [Duplicati](https://github.com/duplicati/duplicati) | 8200 | `8200` |
| [FileBrowser](https://github.com/filebrowser/filebrowser) | 22534 | `22534` |
| [Gitea](https://github.com/go-gitea/gitea) | 3000 | `3000` |
| [Gogs](https://github.com/gogs/gogs) | 3000 | `3002` |
| [Jackett](https://github.com/Jackett/Jackett) | 9117 | `9117` |
| [Linkwarden](https://github.com/linkwarden/linkwarden) | 3000 | `3003` |
| [Netdata](https://github.com/netdata/netdata) | 19999 | `19999` |
| [OpenGist](https://github.com/thomiceli/opengist) | 6157 | `6157` |
| [Portainer](https://github.com/portainer/portainer) | 9443 | `9443` |
| [Prowlarr](https://github.com/Prowlarr/Prowlarr) | 9696 | `9696` |
| [qBittorrent](https://github.com/qbittorrent/qBittorrent) | 8081 | `8081` |
| [ShellInABox](https://github.com/shellinabox/shellinabox) | 4200 | `4200` |
| [Sonarr](https://github.com/Sonarr/Sonarr) | 8989 | `8989` |
| [Swizzin](https://github.com/swizzin/swizzin) | 8333 | `8333` |
| [Syncthing](https://github.com/syncthing/syncthing) | 8384 | `8384` |
| [TheLounge](https://github.com/thelounge/thelounge) | 9000 | `9000` |
| [Uptime Kuma](https://github.com/louislam/uptime-kuma) | 3001 | `3001` |
| [Webmin](https://github.com/webmin/webmin) | 10000 | `10000` |

<br />

---

<br />

## Trademark Disclaimer
All trademarks, logos and brand names are the property of their respective owners. All company, product and service names used in this repository are for identification purposes only. Use of these names, trademarks and brands does not imply endorsement.

<br />

---

<br />

## Contributors ✨
We are always looking for contributors. If you feel that you can provide something useful to Gistr, then we'd love to review your suggestion. Before submitting your contribution, please review the following resources:

- [Pull Request Procedure](.github/PULL_REQUEST_TEMPLATE.md)
- [Contributor Policy](CONTRIBUTING.md)

<br />

Want to help but can't write code?
- Review [active questions by our community](https://github.com/Aetherinox/searxico-cdn/labels/help%20wanted) and answer the ones you know.

<br />

The following people have helped get this project going:

<br />

<div align="center">

<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![Contributors][contribs-all-img]](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top"><a href="https://gitlab.com/Aetherinox"><img src="https://avatars.githubusercontent.com/u/118329232?v=4?s=40" width="80px;" alt="Aetherinox"/><br /><sub><b>Aetherinox</b></sub></a><br /><a href="https://github.com/Aetherinox/searxico-worker/commits?author=Aetherinox" title="Code">💻</a> <a href="#projectManagement-Aetherinox" title="Project Management">📆</a> <a href="#fundingFinding-Aetherinox" title="Funding Finding">🔍</a></td>
    </tr>
  </tbody>
</table>
</div>
<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

<br />
<br />

<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->

<!-- BADGE > GENERAL -->
  [general-npmjs-uri]: https://npmjs.com
  [general-nodejs-uri]: https://nodejs.org
  [general-npmtrends-uri]: http://npmtrends.com/searxico-cdn

<!-- BADGE > VERSION > GITHUB -->
  [github-version-img]: https://img.shields.io/github/v/tag/Aetherinox/searxico-cdn?logo=GitHub&label=Version&color=ba5225
  [github-version-uri]: https://github.com/Aetherinox/searxico-cdn/releases

<!-- BADGE > VERSION > NPMJS -->
  [npm-version-img]: https://img.shields.io/npm/v/searxico-cdn?logo=npm&label=Version&color=ba5225
  [npm-version-uri]: https://npmjs.com/package/searxico-cdn

<!-- BADGE > VERSION > PYPI -->
  [pypi-version-img]: https://img.shields.io/pypi/v/searxico-cdn-plugin
  [pypi-version-uri]: https://pypi.org/project/searxico-cdn-plugin/

<!-- BADGE > LICENSE > MIT -->
  [license-mit-img]: https://img.shields.io/badge/MIT-FFF?logo=creativecommons&logoColor=FFFFFF&label=License&color=9d29a0
  [license-mit-uri]: https://github.com/Aetherinox/searxico-cdn/blob/main/LICENSE

<!-- BADGE > GITHUB > DOWNLOAD COUNT -->
  [github-downloads-img]: https://img.shields.io/github/downloads/Aetherinox/searxico-cdn/total?logo=github&logoColor=FFFFFF&label=Downloads&color=376892
  [github-downloads-uri]: https://github.com/Aetherinox/searxico-cdn/releases

<!-- BADGE > NPMJS > DOWNLOAD COUNT -->
  [npmjs-downloads-img]: https://img.shields.io/npm/dw/%40aetherinox%2Fsearxico-cdn?logo=npm&&label=Downloads&color=376892
  [npmjs-downloads-uri]: https://npmjs.com/package/searxico-cdn

<!-- BADGE > GITHUB > DOWNLOAD SIZE -->
  [github-size-img]: https://img.shields.io/github/repo-size/Aetherinox/searxico-cdn?logo=github&label=Size&color=59702a
  [github-size-uri]: https://github.com/Aetherinox/searxico-cdn/releases

<!-- BADGE > NPMJS > DOWNLOAD SIZE -->
  [npmjs-size-img]: https://img.shields.io/npm/unpacked-size/searxico-cdn/latest?logo=npm&label=Size&color=59702a
  [npmjs-size-uri]: https://npmjs.com/package/searxico-cdn

<!-- BADGE > CODECOV > COVERAGE -->
  [codecov-coverage-img]: https://img.shields.io/codecov/c/github/Aetherinox/searxico-cdn?token=XXXXXXGIOG&logo=codecov&logoColor=FFFFFF&label=Coverage&color=354b9e
  [codecov-coverage-uri]: https://codecov.io/github/Aetherinox/searxico-cdn

<!-- BADGE > ALL CONTRIBUTORS -->
  [contribs-all-img]: https://img.shields.io/github/all-contributors/Aetherinox/searxico-cdn?logo=contributorcovenant&color=de1f6f&label=contributors
  [contribs-all-uri]: https://github.com/all-contributors/all-contributors

<!-- BADGE > GITHUB > BUILD > NPM -->
  [github-build-img]: https://img.shields.io/github/actions/workflow/status/Aetherinox/searxico-cdn/release.yml?logo=github&logoColor=FFFFFF&label=Build&color=%23278b30
  [github-build-uri]: https://github.com/Aetherinox/searxico-cdn/actions/workflows/release.yml

<!-- BADGE > GITHUB > BUILD > Pypi -->
  [github-build-pypi-img]: https://img.shields.io/github/actions/workflow/status/Aetherinox/searxico-cdn/release-pypi.yml?logo=github&logoColor=FFFFFF&label=Build&color=%23278b30
  [github-build-pypi-uri]: https://github.com/Aetherinox/searxico-cdn/actions/workflows/pypi-release.yml

<!-- BADGE > GITHUB > TESTS -->
  [github-tests-img]: https://img.shields.io/github/actions/workflow/status/Aetherinox/searxico-cdn/tests.yml?logo=github&label=Tests&color=2c6488
  [github-tests-uri]: https://github.com/Aetherinox/searxico-cdn/actions/workflows/tests.yml

<!-- BADGE > GITHUB > COMMIT -->
  [github-commit-img]: https://img.shields.io/github/last-commit/Aetherinox/searxico-cdn?logo=conventionalcommits&logoColor=FFFFFF&label=Last%20Commit&color=313131
  [github-commit-uri]: https://github.com/Aetherinox/searxico-cdn/commits/main/

<!-- prettier-ignore-end -->
<!-- markdownlint-restore -->
