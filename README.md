# Couchptato daemon container

Run couchpotato allowing you to specify USER_UID and USER_GID, so you
will not have permission problems.

## Example

```
docker run -e TZ=America/Argentina/Buenos_Aires \
  -e USER_ID=`id -u` \
  -e USER_GID=`id -g` \
  -p 5050:5050 \
  -v `pwd`/couchpotato:/couchpotato \
  -v `pwd`/movies:/movies \
  --volumes-from transmission \
  -d \
  --name=couchpotato \
  chrodriguez/couchpotato

```

In the above example, we mount volumes from transmission container so downloaded
movies can be managed by couchpotato. You need to configue this integration
properly
