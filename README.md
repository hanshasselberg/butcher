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
