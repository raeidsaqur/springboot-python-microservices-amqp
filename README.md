# Inter-services communicaton using AQMP Brokers

Exploring inter-services communication using AQMP brokers like RabbitMQ among python and java based microservices.

## Setup
*cd* into each of the front-end, backend services directory and initiate them:

```
vagrant up --provider virtualbox

java-api-backend$ gradle run
java-api-backend$ cd ../knockout-frontend

knockout-frontend$ python -m SimpleHTTPServer 8090
knockout-frontend$ cd ../python-scraping-service

python-scraping-service$ pip install -r requirements.txt
python-scraping-service$ python worker.py

```

### Prerequisites

_Note_: You must have *wget* and *apt-get* installed on Mac OS X for the vagrant scripts to execute successfully.

_To install *wget*, simply run:_ `brew install wget`



### Vagrant Setup

I've used virtualbox with ubuntu/trusty64 environment for running this. If you don't have it setup, the easiest to do this in Mac OS X is using Homebrew Cask:

##### Install

```
	$ brew cask install virtualbox
	$ brew cask install vagrant
```
_Vagrant Manager_ helps you manage all your VMs in one place from menubar

```
	$ brew cask install vagrant-manager
```
Every Vagrant development environment requires a box. You can search for boxes at [link][2]

The virtual box used for this demo is ubuntu/trusty64 [link][3]

```
	$ vagrant init ubuntu/trusty64; 
```
You should get a CL message: _A `Vagrantfile` has been placed in this directory. You are now ready to `vagrant up` your first virtual environment! Please read
the comments in the Vagrantfile as well as documentation on
`vagrantup.com` for more information on using Vagrant._

```
	$ vagrant up --provider virtualbox
```

![alt text][vagrant-up]

To get rid of the vagrant VM, just run `vagrant destroy`

**Note**: to make things easier, in application.properties the line spring.jpa.hibernate.ddl-auto=create allows us to automatically create the tables when starting up. However, this means all tables get erased with each new start. Change the line to spring.jpa.hibernate.ddl-auto=validate (after you have started up the backend at least once) to avoid data loss.


### Python Modules and Requirements

[Pika link][1]: Pika is a pure-Python implementation of the AMQP 0-9-1 protocol that tries to stay fairly independent of the underlying network support library.

### Spring-boot Java Requirements

Spring has a boot starter module available for RabbitMQ [link][4] `org.springframework.boot:spring-boot-starter-amqp`, which we add to our dependencies.


### Knockout JS front-end Requirements

### Reference:

1. [https://pika.readthedocs.io/en/0.10.0/index.html][1]
2. [https://atlas.hashicorp.com/boxes/search][2]
3. [https://atlas.hashicorp.com/ubuntu/boxes/trusty64][3]
4. [Spring Boot RabbitMQ][4]

[vagrant-up]: https://github.com/raeidsaqur/springboot-python-microservices-amqp/blob/develop/docs/vagrant-up.png "vagrant up CLI message"

[1]: https://pika.readthedocs.io/en/0.10.0/index.html
[2]: https://atlas.hashicorp.com/boxes/search
[3]: https://atlas.hashicorp.com/ubuntu/boxes/trusty64
[4]: https://spring.io/guides/gs/messaging-rabbitmq/


