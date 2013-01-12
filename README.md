# The Butcher

Batch service in nginx!

## Installation

Follow http://openresty.org/#Installation.

## Start

```
/usr/local/openresty/nginx/sbin/nginx -p `pwd`/ -c conf/nginx.conf
```

## Request

```
curl --data '{"ops":[{"method":"get","url":"/me"}, {"method":"get","url":"/me/tasks"}]}' localhost:8080/batch
```
