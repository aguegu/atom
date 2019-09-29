Compile Atom on raspbian

1. Grab a Raspberry Pi 4 (4GB RAM recommended) with latest Raspbian OS.

2. Install docker

3. clone this repo locally and cd into it

4. Go to the arm32v7 folder: `cd arm32v7/`

5. Create Atom builder image: `make builder`

6. Build Atom deb package within the builder image: `make deb`. It would take almost an hour. Run some process monitor, like `htop`, to see it is ongoing.

7. If everything works fine, you would get `../out/atom-armhf.deb`.

8. `cd ../out && dpkg -i atom-armhf.deb`

9. If some dependencies are missed, `sudo apt --fix-broken install && dpkg -i atom-armhf.deb`

10. Then you got `atom-dev` in `/usr/bin`
