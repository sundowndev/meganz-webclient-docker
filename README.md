# MEGA Web Client Docker Image

This repository builds an unofficial Docker image for the [mega.nz web client](https://github.com/meganz/webclient). This image can be pulled from Docker hub as `sundowndev/meganz-webclient`.

Image is built nightly and pushed to the following channels:

| Description | Tags | Platforms |
|-------------|-------|-----------|
| Apache Image | `latest`, `apache` | `amd64` |

## Background

MEGA.nz is a great for cloud storage solution for individuals and businesses. It uses E2EE and their front applications are free and open source. MEGA offers great guarantee that your files are strongly encrypted, and you're the only one that can decrypt those files. However, MEGA users cannot be sure that the official website will always serve open source JavaScript to their browser. Your web browser trusts whatever it receives from MEGA, which means they can grab your master key whenever you visit their site and then use it to decrypt and read your files. You'd never know. [MegaPWN](https://nzkoz.github.io/MegaPWN/) demonstrated that attack vector with a bookmarklet that could lead to leak your MEGA master key.

> "Technically, we could serve you backdoored JavaScript code that sends your master encryption key back to us." [MEGA](https://mega.nz/blog/new-zealand-storage-node-now-live)

This repository aims to reduce risk of receiving of backdoored JavaScript code from the [MEGA web application](https://mega.nz/). Deploy this Docker image online or locally and access your files as usual, with confidence that assets were built from source.

**References**

- https://nzkoz.github.io/MegaPWN/
- https://mega.nz/blog/new-zealand-storage-node-now-live

## Using the apache image

The apache image contains a webserver and exposes port 80. To start the container type:

```shell
$ docker run -d -p 8080:80 sundowndev/meganz-webclient:apache
```

Now you can access MEGA at http://localhost:8080/ from your host system.

## License

Code in this repository is [MIT licensed](https://github.com/sundowndev/meganz-webclient-docker/blob/main/LICENSE).
