
# Bitnami Symfony Development Container

> Note that this is a development container that includes the [`symfony` command-line tool](https://symfony.com/blog/introducing-the-new-symfony-installer).
> This allows you to create a project based on any version of symfony.

## TL;DR;

### Local workspace

```bash
$ mkdir ~/myapp && cd ~/myapp
$ curl -LO https://raw.githubusercontent.com/bitnami/bitnami-docker-symfony/master/docker-compose.yml
$ docker-compose up
```

## Why use Bitnami Images?

* Bitnami closely tracks upstream source changes and promptly publishes new versions of this image using our automated systems.
* With Bitnami images the latest bug fixes and features are available as soon as possible.
* Bitnami containers, virtual machines and cloud images use the same components and configuration approach - making it easy to switch between formats based on your project needs.
* All our images are based on [minideb](https://github.com/bitnami/minideb) a minimalist Debian based container image which gives you a small base container image and the familiarity of a leading linux distribution.
* Bitnami container images are released daily with the latest distribution packages available.


> This [CVE scan report](https://quay.io/repository/bitnami/symfony?tab=tags) contains a security report with all open CVEs. To get the list of actionable security issues, find the "latest" tag, click the vulnerability report link under the corresponding "Security scan" field and then select the "Only show fixable" filter on the next page.

# How to deploy Symfony in Kubernetes?

You can find an example for testing in the file `test.yaml`. To launch this sample file run:

```bash
$ kubectl apply -f test.yaml
```

> NOTE: If you are pulling from a private containers registry, replace the image name with the full URL to the docker image. E.g.
>
> - image: 'your-registry/image-name:your-version'

## Supported tags and respective `Dockerfile` links

> NOTE: Debian 8 images have been deprecated in favor of Debian 9 images. Bitnami will not longer publish new Docker images based on Debian 8.

Learn more about the Bitnami tagging policy and the difference between rolling tags and immutable tags [in our documentation page](https://docs.bitnami.com/containers/how-to/understand-rolling-tags-containers/).


* [`1-ol-7`, `1.5.11-ol-7-r292` (1/ol-7/Dockerfile)](https://github.com/bitnami/bitnami-docker-symfony/blob/1.5.11-ol-7-r292/1/ol-7/Dockerfile)
* [`1-debian-9`, `1.5.11-debian-9-r270`, `1`, `1.5.11`, `1.5.11-r270`, `latest` (1/debian-9/Dockerfile)](https://github.com/bitnami/bitnami-docker-symfony/blob/1.5.11-debian-9-r270/1/debian-9/Dockerfile)

Subscribe to project updates by watching the [bitnami/symfony GitHub repo](https://github.com/bitnami/bitnami-docker-symfony).

## Introduction

[Symfony](https://symfony.com/), is a web application framework written in [PHP](http://www.php.net) under [MIT License](http://symfony.com/doc/current/contributing/code/license.html).

The Bitnami Symfony Development Container has been carefully engineered to provide you and your team with a highly reproducible Symfony development environment. We hope you find the Bitnami Symfony Development Container useful in your quest for world domination. Happy hacking!

[Learn more about Bitnami Development Containers.](https://docs.bitnami.com/containers/how-to/use-bitnami-development-containers/)

## Getting started

The quickest way to get started with the Bitnami Symfony Development Container is using [docker-compose](https://docs.docker.com/compose/).

Begin by creating a directory for your Symfony application:

```bash
$ mkdir ~/myapp
$ cd ~/myapp
```

Download the [docker-compose.yml](https://raw.githubusercontent.com/bitnami/bitnami-docker-symfony/master/docker-compose.yml) file in the application directory:

```bash
$ curl -LO https://raw.githubusercontent.com/bitnami/bitnami-docker-symfony/master/docker-compose.yml
```

Finally launch the Symfony application development environment using:

```bash
$ docker-compose up
```

The above command creates a container service for Symfony development and bootstraps a new Symfony application, named `myapp` in working directory. You can use your favorite IDE for developing the application.

After the built-in PHP application server has been started, visit http://localhost:8000 in your favorite web browser and you'll be greeted by the Symfony welcome page.

## Executing commands

Commands can be launched inside the `myapp` Symfony Development Container with `docker-compose` using the [exec](https://docs.docker.com/compose/reference/exec/) command.

> **Note**:
>
> The `exec` command was added to `docker-compose` in release [1.7.0](https://github.com/docker/compose/blob/master/CHANGELOG.md#170-2016-04-13). Please ensure that you're using `docker-compose` version `1.7.0` or higher.

The general structure of the `exec` command is:

```bash
$ docker-compose exec <service> <command>
```
where `<service>` is the name of the container service as described in the `docker-compose.yml` file and `<command>` is the command you want to launch inside the service.

Following are a few examples:

- Create a new project named `foo`:

  ```bash
  $ docker-compose run myapp nami execute symfony createProject foo
  ```

- Create a new project named `bar` which uses Symfony version `2.5.0`

  ```bash
  $ docker-compose run myapp nami execute symfony createProject "bar 2.5.0"
  ```

  Note: In the above two examples the `docker-compose.yml` file should be updated so that the `SYMFONY_PROJECT_NAME` specifies the project name that should be served my the PHP application server.

## Issues

If you encountered a problem running this container, you can file an [issue](../../issues/new). For us to provide better support, be sure to include the following information in your issue:

- Host OS and version (`$ uname -a`)
- Docker version (`$ docker version`)
- Docker info (`$ docker info`)
- Docker image version (`$ echo $BITNAMI_IMAGE_VERSION` inside the container)
- Steps to reproduce the issue.

## License

Copyright (c) 2015-2019 Bitnami

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  <http://www.apache.org/licenses/LICENSE-2.0>

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
