# docker-headphones
Installs headphones into a Linux container

![headphones](https://github.com/rembo10/headphones/raw/master/data/images/headphoneslogo.png)

## Description
Headphones is an automated music downloader for NZB and Torrent, written in Python. It supports SABnzbd, NZBget, Transmission, µTorrent, Deluge and Blackhole.

https://github.com/rembo10/headphones

## Usage

    docker create --name=headphones  \
      -v /etc/localtime:/etc/localtime:ro \
      -v <path to headphones config>:/opt/headphones/setup.cfg \
      -v <path to headphones logs>:/opt/headphones/logs \
      -e DOCKUID=<UID default:10016> \
      -e DOCKGID=<GID default:10016> \
      -p 8181:8181/udp digrouz/docker-headphones headphones

## Environment Variables

When you start the `headphones` image, you can adjust the configuration of the `headphones` instance by passing one or more environment variables on the `docker run` command line.

### `DOCKUID`

This variable is not mandatory and specifies the user id that will be set to run the application. It has default value `10016`.

### `DOCKGID`

This variable is not mandatory and specifies the group id that will be set to run the application. It has default value `10016`.

## Notes

* The docker entrypoint will upgrade operating system at each startup.
