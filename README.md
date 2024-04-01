# Food Trucks Search

Welcome to the Food Trucks Search project repository! This project provides a Flask web application to search for food trucks data stored in Elasticsearch. It also includes Docker Compose configurations to set up Elasticsearch, Flask app, and Nginx server.

## Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/food-trucks-search.git
cd food-trucks-search
```

### 2. Run the Application

```bash
docker-compose up --build
```

This command builds the necessary Docker images and starts the containers.

### 3. Access the Application

Once the containers are up and running, you can access the application at [http://localhost:8080](http://localhost:8080).

## Usage

### Searching for Food Trucks

You can search for food trucks by sending a GET request to the `/search` endpoint with a query parameter `q` specifying the search query.

**Example:**

```
GET /search?q=burrito
```

This will return a JSON response containing information about food trucks matching the search query.

### Debugging Elasticsearch

To check the status of Elasticsearch or debug Elasticsearch related issues, you can visit the `/debug` endpoint.

**Example:**

```
GET /debug
```

This will return the status of Elasticsearch.

## Technologies Used

- Flask
- Elasticsearch
- Docker
- Docker Compose
- Nginx