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
$ curl --data '{"ops":[{"method":"get","url":"/me"}, {"method":"get","url":"/me/tasks"}]}' localhost:8080/batch
{"results":[{"status":200,"header":{"Content-Type":"application\/json"},"body":"{\"name\":\"Hans\"}\n"},{"status":200,"header":{"Content-Type":"application\/json"},"body":"[{\"title\": \"build batch service in nginx\"}]\n"}]}
```
