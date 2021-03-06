This repo forks from and3rson/django-nameko.
several improves:

* fix rpc module not found bug in python3

# django-nameko

![build status](https://api.travis-ci.org/and3rson/django-nameko.svg)

Django wrapper for [Nameko] microservice framework.

# How to use

```python
from django_nameko import get_pool           

# Within some view or model:
with get_pool().next() as n:
    n.rpc.mailer.send_mail(foo='bar')
```

# Installation

```sh
pip install django-nameko
```

# Configuration

```python
# Config to be passed to ClusterRpcProxy 
NAMEKO_CONFIG = { 
    'AMQP_URI': 'pyamqp://<username>:<password>@127.0.0.1:5672/<vhost>'
}  

# Number of proxies to create
NAMEKO_POOL_SIZE = 4
```

# Credits
Thanks to guys who made an awesome [Nameko] framework.

[Nameko]: https://github.com/onefinestay/nameko
