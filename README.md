# Vaban

*A quick and easy way to control groups of Varnish cache servers using a RESTful JSON API.*

This is still an early version but its fully working and more features are
planned.

## Install Vaban:

**Run Vaban**

``` sh
go get github.com/ant0ine/go-json-rest/rest
go build vaban.go
./vaban
```

## API Examples using curl

#### Get status of Vaban

``` sh
curl -i http://127.0.0.1:3000/
```

#### Getting the servers in a group

``` sh
curl -i http://127.0.0.1:3000/v1/service/group1
```

#### Sending ping to servers to see that the port is open

``` sh
curl -i http://127.0.0.1:3000/v1/service/group1/ping
```

#### Ban the only the root (/) of your website.

``` sh
curl -i http://127.0.0.1:3000/v1/service/group1/ban -d '{"Pattern":"/"}'
```

#### Ban all css files

``` sh
curl -i http://127.0.0.1:3000/v1/service/group1/ban -d '{"Pattern":".*css"}'
```
