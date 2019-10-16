# geowebcache
Geowebcache docker images, meant to be used with configurations.
Work in progress

### To build
Native JAI on tomcat does work.
```docker build --rm -t terrabrasilis/geowebcache:v1.0 .```

### To RUN
```docker run -d --rm --name "geowebcache" -p 8083:8080 -t -v $(pwd)/config:/config -v $(pwd)/cache:/cache terrabrasilis/geowebcache:v1.0```


### To reload configuration

```
curl -u geowebcache:secured -d "reload_configuration=1" http://localhost:8083/geowebcache/rest/reload
```

#### URL to test
http://localhost:8083/geowebcache/service/wms?service=WMS&request=GetMap&layers=prodes-cerrado%3Alimite_cerrado&styles=&format=image%2Fpng&transparent=true&version=1.1.1&tiled=true&_name=limite_cerrado&_baselayer=false&width=256&height=256&srs=EPSG%3A3857&bbox=-5009377.085697311,-1252344.2714243263,-3757032.814272984,0