# RabbitMQ Messaging Demo

A simple demonstration of message publishing and consuming using RabbitMQ in Python.

## Prerequisites

- Windows OS
- Visual Studio Code
- Docker Desktop
- Python

## Installation & Setup

### 1. Install Required Software

- Install [Visual Studio Code](https://code.visualstudio.com/download)
- Install [Docker Desktop](https://www.docker.com/products/docker-desktop)
- Install [Python](https://www.python.org/downloads/) (if not already installed)

### 2. Start RabbitMQ Server

Run the following command to start a RabbitMQ server in Docker:

```bash
docker run -d --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:management
```

Verify that the container is running:

```bash
docker ps
```

You should see your RabbitMQ container in the list.

### 3. Access RabbitMQ Management Interface

Open a browser and navigate to:
```
http://localhost:15672/
```

Login with the default credentials:
- Username: guest
- Password: guest

### 4. Install Python Libraries

Open a command prompt and install the required Python packages:

```bash
pip install pika
pip install time
```

## Running the Demo

### 1. Clone This Repository

```bash
git clone https://github.com/dormicha67/rabbitmq-demo.git
cd rabbitmq-demo
```

### 2. Run the Consumer

Open a command prompt and run:

```bash
python consumer.py
```

The consumer will start and wait for messages.

### 3. Run the Publisher

Open another command prompt and run:

```bash
python publisher.py
```

The publisher will send 10 messages to RabbitMQ.

## Expected Behavior

### Publisher
The publisher will send 10 messages to RabbitMQ. You should see output similar to:
```
[x] Sent message: 'Message 1'
[x] Sent message: 'Message 2'
...
[x] Sent message: 'Message 10'
```

### Consumer
The consumer will receive and process these messages. You should see output similar to:
```
[x] Received message: 'Message 1'
[x] Received message: 'Message 2'
...
[x] Received message: 'Message 10'
```

## Troubleshooting

- If the Docker container fails to start, ensure Docker Desktop is running
- If you cannot access the RabbitMQ management interface, check that the container is running with `docker ps`
- If messages aren't being received, verify that both the publisher and consumer are using the same queue name

## Additional Information

- RabbitMQ Management UI is accessible at http://localhost:15672/
- The default exchange is used in this demo

