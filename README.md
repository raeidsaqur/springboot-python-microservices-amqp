# Inter-services communicaton using AQMP Brokers

Exploring inter-services communication using AQMP brokers like RabbitMQ among python and java based microservices.

## Setup
*cd* into each of the front-end, backend services directory and initiate them:

```
java-api-backend$ gradle run
java-api-backend$ cd ../knockout-frontend

knockout-frontend$ python -m SimpleHTTPServer 8090
knockout-frontend$ cd ../python-scraping-service

python-scraping-service$ pip install -r requirements.txt
python-scraping-service$ python worker.py

```

### Python Modules and Requirements

[Pika link][1]: Pika is a pure-Python implementation of the AMQP 0-9-1 protocol that tries to stay fairly independent of the underlying network support library.

### Spring-boot Java Requirements

### Knockout JS front-end Requirements

### Reference:

1. [https://pika.readthedocs.io/en/0.10.0/index.html][1]

[1]: https://pika.readthedocs.io/en/0.10.0/index.html
