# dockerFileFFMpegForTest
The goal of this project is to do some test for GCC code generator. 

We will use ffmpeg as a playground to test some ffmpeg variants and we will spy efficiency to detect some inconsistencies in non functional properties of FFMpeg

#FFmpeg command
We could use this [site](http://rodrigopolo.com/ffmpeg/cheats.php) for the ffmpeg option.

To build your ffmpeg image. Go to the correct folder and run.
```bash
docker build .
```
To rename the procude image
```bash
docker images #list the images your get
docker tag d583c3ac45fd myname/server:latest #d583c3ac45fd must be the id of the produced image
```


To run ffmpeg in top of docker. Just use the following command

```bash
docker -i -v /tmp:/tmp -t yourimagename /root/ffmpeg <options>
```

To run [Cadvisor](https://github.com/google/cadvisor)

```bash
sudo docker run \
  --volume=/:/rootfs:ro \
  --volume=/var/run:/var/run:rw \
  --volume=/sys:/sys:ro \
  --volume=/var/lib/docker/:/var/lib/docker:ro \
  --publish=8080:8080 \
  --detach=true \
  --name=cadvisor \
  google/cadvisor:latest
  ```
