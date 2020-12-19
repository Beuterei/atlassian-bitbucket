[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <img src="https://wac-cdn.atlassian.com/dam/jcr:01f0ea80-2b31-4009-8eaf-da8ebcabdfe1/Bitbucket-blue.svg?cdnVersion=1209" alt="Logo" height="60">

  <h3 align="center">atlassian/bitbucket</h3>

  <p align="center">
    Docker setup for bitbucket
    <br />
    <br />
    ·
    <a href="https://github.com/beuluis/atlassian-bitbucket/issues">Report Bug</a>
    ·
    <a href="https://github.com/beuluis/atlassian-bitbucket/issues">Request Feature</a>
  </p>
</p>

<!-- ABOUT THE PROJECT -->

## About The Project

Small docker setup for bitbucket. The production environment also uses [jwilder/nginx-proxy](https://github.com/nginx-proxy/nginx-proxy) and [nginx-proxy/docker-letsencrypt-nginx-proxy-companion](https://github.com/nginx-proxy/docker-letsencrypt-nginx-proxy-companion).

<!-- GETTING STARTED -->

## Getting Started Develop

To get a local copy up and running follow these simple steps.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)

### Installation

1. Clone the repo

```sh
git clone https://github.com/beuluis/atlassian-bitbucket.git
```

2. Start docker-compose

```sh
docker-compose up --build
```

3. Navigate to `localhost:8097`
4. Follow setup instructions

### Customization

1. Create a `.env` file

```sh
touch .env
```

2. Overwrite variables as you like (format: `{variable name}={variable value}`)

| Variable                       | Description                                   | Default value            | Required |
| ------------------------------ | --------------------------------------------- | ------------------------ | -------- |
| `BITBUCKET_MEMORY`             | Defines how much memory the container can use | `4G`                     | false    |
| `BITBUCKET_JVM_MINIMUM_MEMORY` | The minimum heap size of the JVM              | `512m`                   | false    |
| `BITBUCKET_JVM_MAXIMUM_MEMORY` | The maximum heap size of the JVM              | `1024m`                  | false    |
| `PORT`                         | Which port is mapped to your host machine     | `8097`                   | false    |
| `PG_DB`                        | Postgres DB name                              | `atlassianBitbucketDev`  | false    |
| `PG_USER`                      | Postgres user                                 | `atlassianBitbucketDev`  | false    |
| `PG_PASSWORD`                  | Postgres password                             | `DFLHjKu8C65zHCbj34rLmR` | false    |

## Getting Started Production

To get a copy up and running follow these simple steps.

### Prerequisites

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [Nginx by me](https://github.com/beuluis/nginx)

### Installation

1. Clone the repo

```sh
git clone https://github.com/beuluis/atlassian-bitbucket.git --branch master
```

2. Create a `.env.prod` file

```sh
touch .env.prod
```

3. Overwrite all variables marked under Customization as required
4. Start docker-compose

```sh
docker-compose --env-file ./.env.prod -f docker-compose.yml -f docker-compose.production.yml up -d
```

5. Navigate to `https://{your-host}`
6. Follow setup instructions

### Customization

1. Create a `.env.prod` file

```sh
touch .env.prod
```

2. Overwrite variables as you like (format: `{variable name}={variable value}`)

| Variable                       | Description                                                     | Default value            | Required |
| ------------------------------ | --------------------------------------------------------------- | ------------------------ | -------- |
| `PROXY_NETWORK_NAME`           | Proxy network name                                              | `nginxproxynet`          | false    |
| `BITBUCKET_MEMORY`             | Defines how much memory the container can use                   | `4G`                     | false    |
| `BITBUCKET_JVM_MINIMUM_MEMORY` | The minimum heap size of the JVM                                | `512m`                   | false    |
| `BITBUCKET_JVM_MAXIMUM_MEMORY` | The maximum heap size of the JVM                                | `1024m`                  | false    |
| `HOST`                         | Host which your container should be accessible. E.g. `test.com` | none                     | true     |
| `PG_DB`                        | Postgres DB name                                                | `atlassianBitbucketProd` | false    |
| `PG_USER`                      | Postgres user                                                   | `atlassianBitbucketProd` | false    |
| `PG_PASSWORD`                  | Postgres password                                               | none                     | true     |

<!-- CONTRIBUTING -->

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<!-- CONTACT -->

## Contact

Luis Beu - me@luisbeu.de

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->

[contributors-shield]: https://img.shields.io/github/contributors/beuluis/atlassian-bitbucket.svg?style=flat-square
[contributors-url]: https://github.com/beuluis/atlassian-bitbucket/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/beuluis/atlassian-bitbucket.svg?style=flat-square
[forks-url]: https://github.com/beuluis/atlassian-bitbucket/network/members
[stars-shield]: https://img.shields.io/github/stars/beuluis/atlassian-bitbucket.svg?style=flat-square
[stars-url]: https://github.com/beuluis/atlassian-bitbucket/stargazers
[issues-shield]: https://img.shields.io/github/issues/beuluis/atlassian-bitbucket.svg?style=flat-square
[issues-url]: https://github.com/beuluis/atlassian-bitbucket/issues
[license-shield]: https://img.shields.io/github/license/beuluis/atlassian-bitbucket.svg?style=flat-square
