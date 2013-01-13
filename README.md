# The Butcher

It is a service implentation of Alex Koppel's [Batch API](https://github.com/arsduo/batch_api) in nginx/lua.
It is not ready yet but enough to see where this is leading to.

The sequential option is ignored and GET requests are fired in parallel.

## Installation

Follow http://openresty.org/#Installation.

## Start

```
/usr/local/openresty/nginx/sbin/nginx -p `pwd`/ -c conf/nginx.conf
```

## Request

```
$ curl -s --data '{"ops":[{"method":"get","url":"/me"}, {"method":"get","url":"/me"}, {"method":"post","url":"/me/tasks"}, {"method":"get","url":"/me"}, {"method":"get","url":"/me"}]}' localhost:8080/batch | python -m json.tool
{
    "results": [
        {
            "body": "{\"name\":\"Hans\"}\n",
            "header": {
                "Content-Type": "application/json"
            },
            "status": 200
        },
        {
            "body": "{\"name\":\"Hans\"}\n",
            "header": {
                "Content-Type": "application/json"
            },
            "status": 200
        },
        {
            "body": "[{\"title\": \"build batch service in nginx\"}]\n",
            "header": {
                "Content-Type": "application/json"
            },
            "status": 200
        },
        {
            "body": "{\"name\":\"Hans\"}\n",
            "header": {
                "Content-Type": "application/json"
            },
            "status": 200
        },
        {
            "body": "{\"name\":\"Hans\"}\n",
            "header": {
                "Content-Type": "application/json"
            },
            "status": 200
        }
    ]
}
```
